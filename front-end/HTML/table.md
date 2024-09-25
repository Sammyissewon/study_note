# `<table>` 태그

1. `<table>`
    
    **역할**: 테이블 전체를 정의하는 루트 태그입니다. 이 태그 내에 다른 모든 테이블 관련 태그들이 들어갑니다.
    
2. `<thead>` (Table Head)
    
    **역할**: 테이블의 헤더 부분을 그룹화합니다. 일반적으로 열 제목을 포함하는 행(`<tr>`)으로 구성됩니다.
    
3. `<tbody>` (Table Body)
    
    **역할**: 테이블의 본문 부분을 그룹화합니다. 여러 행(`<tr>`)을 포함하며, 주로 테이블의 데이터를 나타냅니다.
    
4. `<tfoot>` (Table Footer)
    
    **역할**: 테이블의 하단(푸터) 부분을 그룹화합니다. 총합이나 요약 정보 등으로 사용되며 `<thead>`와 `<tbody>`와 함께 사용됩니다.
    
5. `<tr>` (Table Row)
    
    **역할**: 테이블의 한 행을 나타냅니다. `<table>` 또는 `<thead>`, `<tbody>`, `<tfoot>` 안에 사용됩니다.
    
6. `<th>` (Table Header Cell)
    
    **역할**: 테이블의 헤더 셀을 정의합니다. 기본적으로 굵은 글씨와 가운데 정렬로 표시됩니다. `<tr>` 태그 내부에서 사용됩니다.
    
7. `<td>` (Table Data Cell)
    
    **역할**: 테이블의 데이터 셀을 정의하며, 테이블의 일반적인 데이터 항목을 나타냅니다. `<tr>` 태그 내부에서 사용됩니다.
    
8. `<caption>`
    
    **역할**: 테이블에 제목 또는 설명을 추가하는 태그입니다. `<table>` 태그 바로 아래에 위치해야 합니다.
    
9. `<colgroup>` (Column Group)
    
    **역할**: 열을 그룹화하여 스타일을 적용하거나 속성을 지정할 때 사용합니다. `<colgroup>` 안에 `<col>` 태그를 포함할 수 있습니다.
    
10. `<col>` (Column)
    
    **역할**: 개별적인 열을 나타내며, 스타일이나 속성을 열에 적용할 때 사용됩니다. `<colgroup>` 태그 안에 위치해야 합니다.

```html
<table>
  <caption>
    Front-end web developer course 2021
  </caption>
  <thead>
    <tr>
      <th scope="col">Person</th>
      <th scope="col">Most interest in</th>
      <th scope="col">Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Chris</th>
      <td>HTML tables</td>
      <td>22</td>
    </tr>
    <tr>
      <th scope="row">Dennis</th>
      <td>Web accessibility</td>
      <td>45</td>
    </tr>
    <tr>
      <th scope="row">Sarah</th>
      <td>JavaScript frameworks</td>
      <td>29</td>
    </tr>
    <tr>
      <th scope="row">Karen</th>
      <td>Web performance</td>
      <td>36</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row" colspan="2">Average age</th>
      <td>33</td>
    </tr>
  </tfoot>
</table>
```

