__[Responsive](#__Responsive__)__</br>
  &nbsp;&nbsp;&nbsp;[HowTo](##HowTo)</br>
  &nbsp;&nbsp;&nbsp;[GridSpan](##GridSpan)</br>
  &nbsp;&nbsp;&nbsp;[ImgResponsiveCss](##ImgResponsiveCss)</br>
  &nbsp;&nbsp;&nbsp;[MeerdereClassesSelecteren](##MeerdereClassesSelecteren)</br>


__[ResponsiveImages](#__ResponsiveImages__)__</br>
  &nbsp;&nbsp;&nbsp;[FullImg/ImgOverHelePagina](##FullImg/ImgOverHelePagina)</br>
  &nbsp;&nbsp;&nbsp;[PartIMG](##PartIMG)</br>
  &nbsp;&nbsp;&nbsp;[WeBPIMG](##WeBPIMG)</br>




# Responsive
## HowTo
```
@media only screen and (min-width: 900px) {
  div::before {
    content: "min-width: 900px";
  }
}
```
```
@media only screen and (orientation: portrait / landscape){
  div::before {
    content: 'portrait';
  }
}
```

### GridSpan

```
grid-column: 1 / span 2;
```

### ImgResponsiveCss
```
.freddy {
    width: 100%;
    margin: 0;
  }
```

### MeerdereClassesSelecteren 
```
  .carriere,
  .vervolg,
  .outro,
  .zeges,
  .palmares {
    grid-column: 1 / span 2;
  }
```

width | doen
------------ | -------------
`Bij min width` | van klein naar groot ➡️ 300 -> 900
`Bij min width` | van groot naar klein ➡️ 900 -> 300


# ResponsiveImages

## FullImg/ImgOverHelePagina

```
<img 
    srcset="
          ./assets/img/regular/beach@0,1x.jpg   100w,
          ./assets/img/regular/beach@0,25x.jpg  250w,
          ./assets/img/regular/beach@0,33x.jpg  333w,
          ./assets/img/regular/beach@0,5x.jpg   500w,
          ./assets/img/regular/beach@0,75x.jpg  750w,
          ./assets/img/regular/beach.jpg       1000w,
          ./assets/img/regular/beach@1,5x.jpg  1500w,
          ./assets/img/regular/beach@1,25x.jpg 1250w,
          ./assets/img/regular/beach@2x.jpg    2000w,
          ./assets/img/regular/beach@3x.jpg    3000w
        " sizes="100vw" class="img--full" src="./assets/img/regular/beach.jpg"
    alt="a lighthouse at the beach by sunset" 
  />

    .img--2thirds {
        width: 100vw;
    }
```

## PartIMG

```
<img srcset="./assets/img/regular/beach.jpg 1000w,
              ./assets/img/regular/beach@0,1x.jpg 100w,
              ./assets/img/regular/beach@0,5x.jpg 500w,
              ./assets/img/regular/beach@0,25x.jpg 250w,
              ./assets/img/regular/beach@0,33x.jpg 333w,
              ./assets/img/regular/beach@0,75x.jpg 750w,
              ./assets/img/regular/beach@1,5x.jpg 1500w,
              ./assets/img/regular/beach@1,25x.jpg 1250w,
              ./assets/img/regular/beach@2x.jpg 2000w,
              ./assets/img/regular/beach@3x.jpg 3000w"
    sizes="66.66vw"
    class="img--2thirds" src="./assets/img/regular/beach.jpg" alt="a lighthouse at the beach by sunset">

    <!-- CSS -->

    .img--2thirds {
        width: 66.66vw;
    }
```

## WeBPIMG
```
<picture>
      <source
        srcset="
          ./assets/img/webp/beach.webp       1000w,
          ./assets/img/webp/beach@0,1x.webp   100w,
          ./assets/img/webp/beach@0,25x.webp  250w,
          ./assets/img/webp/beach@0,33x.webp  333w,
          ./assets/img/webp/beach@0,5x.webp   500w,
          ./assets/img/webp/beach@0,75x.webp  750w,
          ./assets/img/webp/beach@1,5x.webp  1500w,
          ./assets/img/webp/beach@1,25x.webp 1250w,
          ./assets/img/webp/beach@2x.webp    2000w,
          ./assets/img/webp/beach@3x.webp    3000w
        "
        sizes="100vw"
        type="image/webp"
      />
      <source
        srcset="
          ./assets/img/regular/beach.jpg       1000w,
          ./assets/img/regular/beach@0,1x.jpg   100w,
          ./assets/img/regular/beach@0,25x.jpg  250w,
          ./assets/img/regular/beach@0,33x.jpg  333w,
          ./assets/img/regular/beach@0,5x.jpg   500w,
          ./assets/img/regular/beach@0,75x.jpg  750w,
          ./assets/img/regular/beach@1,5x.jpg  1500w,
          ./assets/img/regular/beach@1,25x.jpg 1250w,
          ./assets/img/regular/beach@2x.jpg    2000w,
          ./assets/img/regular/beach@3x.jpg    3000w
        "
        sizes="100vw"
        type="image/jpeg"
      />
      <img
        class="img--full"
        src="./assets/img/regular/beach.jpg"
        alt="a lighthouse at the beach by sunset"
      />
    </picture>
```
