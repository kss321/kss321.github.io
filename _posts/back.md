######BO에 고정된 텍스트를 넣을 때

```java
@UiGridCellFormatter(grid = "grid", propertyId = "emailBody")
public void gridCellFormat(GridRowRenderer.CellFormatterContext ctx) {
    ctx.cell.text = "本文";
}
```

######버튼 추가시

BO의 화면일람에서 소스를 생성

MenuUi_ecp-bo.sql에서 해당하는 버튼의 insert문 찾기

DB에서 실행

소스 관리를 위해 MenuUi_ecp-bo.sql에 해당 insert문 추가

BO의 ロール及び権限詳細에서 해당하는 화면의 권한 체크