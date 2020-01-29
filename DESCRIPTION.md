# GRID 패턴

이 저장소는 Grid 패턴에 대해 간단한 설명을 하기 위해 생성되었습니다.

### Grid 패턴이란?
==============

grid는 flex와 비슷하게 격자 단위의 레이아웃을 짤 때 사용하는 CSS의 **'display'** 속성중 하나입니다.
flex에 비해서 더 편리한 점은 불규칙적인 레이아웃을 작성할 때 유용하다는 것입니다.

일단, grid를 구성하는 HTML를 보도록 하겠습니다.

```
<h1>Grid Gallery</h1>
<section id="gallery">
    <div class="image" style="background-image: url(images/busan.jpg)" data-name="BUSAN"></div>
    <div class="image" style="background-image: url(images/damyang.jpg)" data-name="DAMYANG"></div>
    <div class="image" style="background-image: url(images/jeju.jpg)" data-name="JEJU"></div>
    <div class="image" style="background-image: url(images/kwangwha.jpg)" data-name="KWANGWHA"></div>
    <div class="image" style="background-image: url(images/kyungbok.jpg)" data-name="KYUNGBOK"></div>
    <div class="image" style="background-image: url(images/kyungju.jpg)" data-name="KYUNGJU"></div>
    <div class="image" style="background-image: url(images/waterbridge.jpg)" data-name="WATER-BRIDGE"></div>
</section>
```

\<section\> 태그가 각각의 이미지를 둘러싸고 있는 구조입니다.
\<img\>태그가 아닌, \<div\>태그를 사용하여 CSS로 이미지를 보여줌으로써, 사이즈에 관계 없이
본래의 해상도를 유지할 수 있도록 작성하였습니다. 하지만 이 글은 grid를 설명하기 위한 글이므로 자세한 설명은 생략하도록 하겠습니다.

```
#gallery {
    margin-top: 50px;
    display: grid;
    grid-auto-rows: 3fr 1.5fr 0.5fr 2fr;
    grid-template-columns: repeat(3, 1fr); 
    grid-gap: 10px;
}

#gallery .image:nth-child(2){ grid-column: 2/4; grid-row: 1/3;}
#gallery .image:nth-last-child(2) { grid-column: 3/4; grid-row: 3/5; }
#gallery .image:nth-last-child(1) { grid-column: 1/3; }
```