####reCAPTCHA

1. 사용목적
    - 스팸 및 자동화 공격으로부터 보호
	
2. 종류
    - reCAPTCHA v3
    - reCAPTCHA v2
        - checkbox
        - badge
        - android


3. reCAPTCHA guides
    - 공식문서 https://developers.google.com/recaptcha/intro?hl=en
    - https://qiita.com/yagi_eng/items/77166b5339196f2c5ad1
    - 적용 예1 https://playon.tistory.com/76
    - 적용 예2 https://swiftcoding.org/recaptcha-api-key
    - 적용 예3 https://github.com/newsfusion/recaptcha-v3-java-
    - 적용 예4 https://www.techscore.com/blog/2018/12/06/recaptcha-v3/
    - 적용 예5 https://codelabs.developers.google.com/codelabs/reCAPTCHA/#0 (v2 의 invisible)
    - 적용 예6 https://www.youtube.com/watch?v=tbvxFW4UJdU

4. 방법
    - https://www.google.com/recaptcha/admin/create에서 API Key pair를 등록
    - Key pair는 site key와 secret key를 가지고 있음
        - site key : reCAPTCHA 서비스를 사이트로 불러옴    
        - secret key : 어플리케이션과 reCAPTCHA 사이에서 Verifying the user's response, 시큐리티상 필요
    - reCAPTCHA 타입을 선택하고 authorized domains이나 package names을 입력 -> accept후, Register 버튼을 클릭하여 새로운 API Key pair를 받을 수 있음

    - reCAPTCHA v3 적용
        - reCAPTCHA v3는 user friction 없이 각각의 리퀘스트에 score를 리턴하는 형태
            - 1.0 -> 정상접근
            - 0.0 -> bot
        - score는 사이트와의 상호작용을 기반으로 함
    - javaScript 작성법
        ```javascript
        <script src="https://www.google.com/recaptcha/api.js?render=_reCAPTCHA_site_key"></script>
        <script>
        grecaptcha.ready(function() {
            grecaptcha.execute('_reCAPTCHA_site_key_', {action: 'homepage'}).then(function(token) {
               ...
            });
        });
        </script>	
        ```		
    - 발급받은 site key와 함께 reCAPTCHA API를 불러온다
    - 페이지가 로드되면 grecaptcha.execute 호출
    - verify request와 함께 백엔드쪽으로 토큰을 보냄
    - 토큰의 2분이 지나면 만료됨, 따라서 call하는 시점을 유저가 액션을 취하는 시점에 excute할 수 있도록 할 것!
    - 같은 페이지 내에서도 여러 actions에 reCAPTCHA v3를 적용할 수 있음
    - v3는 스코어를 리턴하는데 이 리턴한 스코어에 따라서 사이트 내에서 다양한 처리를 할 수 있음
    - v3는 사이트의 트래픽을 보고 학습함
    - 액션
       ```javascript
        <script>
        grecaptcha.ready(function() {
            grecaptcha.execute('reCAPTCHA_site_key', {action: 'homepage'});
        });
        </script>
        ```
        액션은 알파벳, 슬래시만 가능하고, 유저를 특정해서는 안됨
    
    - Site Verify Response
        ```json
        {
          "success": true|false,      		// whether this request was a valid reCAPTCHA token for your site
          "score": number             		// the score for this request (0.0 - 1.0)
          "action": string            			// the action name for this request (important to verify)
          "challenge_ts": timestamp,  	// timestamp of the challenge load (ISO format yyyy-MM-dd'T'HH:mm:ssZZ)
          "hostname": string,         		// the hostname of the site where the reCAPTCHA was solved
          "error-codes": [...]        		// optional
        }
       ```
       
5. Example       
    ```html
    <script src="https://www.google.com/recaptcha/api.js?render=（サイトキー）"></script>
    <form>
      <div><input type="submit" value="등록"></div>
      <input type="hidden" id="recaptchaResponse" name="g-recaptcha">
    </form>
    ```

    ```java
    @RequestMapping(value = "/hoge", method = RequestMethod.POST)
    public String hogePost(
            @Valid @ModelAttribute("hogeForm") HogeForm hogeForm,
            BindingResult bindingResult,
            HttpServletRequest request, SitePreference sitePreference, Model model) {
    
        String url = "https://www.google.com/recaptcha/api/siteverify?secret=" + （シークレットキー） + "&response=" + hogeForm.getRecaptchaResponse;
        RestTemplate restTemplate = new RestTemplate();
        RecaptchaResult result = restTemplate.getForObject(url, RecaptchaResult.class);
    
        log.info("reCAPTCHA result: " + result.toString());
    
        if (result.isSuccess()) {
            if ( 0.5 <= result.getScore()) {
                // BOTと判定されなかった場合の処理を記述
            } else {
                // BOTと判定された場合の処理を記述
            }
        } else {
            // reCAPTCHAに接続失敗した場合の処理を記述
        }
    }
    ```

    ```javascript
    $form = $(/* formを取得 */);
    $button = $(/* form内のsubmitボタンを取得 */);
    
    $button.click(function() {
        // reCAPTCHA v3用
        grecaptcha.ready(function () {
            grecaptcha.execute(（サイトキー）, {action: 'contact_form'}).then(function(token) {
                $('#recaptcha-response').val(token);
    
                // reCAPTCHA実装前に関数内に記述していた処理はここに記述              
    
                $form.submit();
            });
        });
    });
    ```