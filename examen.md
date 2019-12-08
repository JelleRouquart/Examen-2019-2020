__[Responsive](#__Responsive__)__</br>
  &nbsp;&nbsp;&nbsp;[HowTo](##HowTo)</br>
  &nbsp;&nbsp;&nbsp;[GridSpan](##GridSpan)</br>
  &nbsp;&nbsp;&nbsp;[ImgResponsiveCss](##ImgResponsiveCss)</br>
  &nbsp;&nbsp;&nbsp;[MeerdereClassesSelecteren](##MeerdereClassesSelecteren)</br>


__[ResponsiveImages](#__ResponsiveImages__)__</br>
  &nbsp;&nbsp;&nbsp;[FullImg/ImgOverHelePagina](##FullImg/ImgOverHelePagina)</br>
  &nbsp;&nbsp;&nbsp;[PartIMG](##PartIMG)</br>
  &nbsp;&nbsp;&nbsp;[WeBPIMG](##WeBPIMG)</br>

__[CSS](#__css__)__</br>
  &nbsp;&nbsp;&nbsp;[Variablen](##Variablen)</br>
  &nbsp;&nbsp;&nbsp;[oproepen](###oproepen)</br>
  &nbsp;&nbsp;&nbsp;[Importeren](##Importeren)</br>
  &nbsp;&nbsp;&nbsp;[berekeningen](###berekeningen)</br>
  &nbsp;&nbsp;&nbsp;[nesten](###nesten)</br>

__[JS](#__JS__)__</br>
  &nbsp;&nbsp;&nbsp;[Variablen](##Variablen)</br>
  &nbsp;&nbsp;&nbsp;[ImportCSS](##ImportCSS)</br>
  &nbsp;&nbsp;&nbsp;[ImportJson](##ImportJson)</br>
  &nbsp;&nbsp;&nbsp;[FindId](##FindId)</br>
  &nbsp;&nbsp;&nbsp;[IfAdd](##IfAdd)</br>


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
<picture class="banner__picture">
        <source srcset="
                ./assets/img/brik_210.webp            210w,
                ./assets/img/brik_350.webp            350w,
                ./assets/img/brik_440.webp            440w,
                ./assets/img/brik_527.webp            527w"
                sizes=" (min-width: 450px) 30vw,
                        (min-width: 700px) 44vw,
                        1px"
                type="image/webp" />
        <source srcset="
                ./assets/img/brik_210.png            210w,
                ./assets/img/brik_250.png            250w,
                ./assets/img/brik_440.png            440w,
                ./assets/img/brik_527.png            527w"
                sizes=" (min-width: 450px) 30vw,
                        (min-width: 700px) 45vw,
                        1px" type="image/png" />
        <img class="banner__image" src="assets/img/brik.png" height="673" width="527" alt="brik met smoothie - bestel nu">
      </picture>
```

## hoe het moet oefeningen  
```
<img class="banner__image" height="673" width="527" src="assets/img/brik_527.png" srcset="assets/img/brik_527.png 527w,
                    assets/img/brik_440.png 440w,
                    assets/img/brik_350.png 350w,
                    assets/img/brik_210.png 210w,
                    assets/img/default.gif 1w" sizes="(min-width: 450px) 30vw,
                    (min-width: 700px) 45vw,
                    1px" alt="brik met smoothie - bestel nu">
```

## Verschillende fotos
```
<picture class="freddy">
  <source media="(max-width: 499px)" srcset="assets/img/freddy_tour_1978_sq.jpg">
  <source media="(max-width: 699px)" srcset="assets/img/freddy_tour_1978_portrait.jpg">
  <source media="(max-width: 899px)" srcset="assets/img/freddy_tour_1978_landscape.jpg">
  <source media="(min-width: 900px)" srcset="assets/img/freddy_tour_1978_full.jpg">
  <img src="./assets/img/freddy.jpg" width="266" height="400" alt="freddy op zine velo">
</picture>
```



# CSS
## Variablen
### aanmaken
```
:root {
  --colorLightest: white;
  --colorText: #211f1f;
  --colorMain: #f9d2cb;
  --colorSecondary: #a3f4dc;
  --colorGray: #fafafa;
  --colorGrayDark: #9c9c9c;
  --spacerSmall: .75rem; /* 12px */
  --spacerRegular: 1rem; /* 16px */
  --spacerBig: 1.88rem; /* 30px */
  --fontSmall: .75rem; /* 12px */
  --fontRegular: 1.13rem; /* 18px */
  --fontMedium: 1.25rem; /* 20px */
  --fontBig: 1.75rem; /* 28px */
  --font: 'Roboto', sans-serif;
  --fontWeightRegular: 400;
  --fontWeightBold: 500;
}

@custom-media --only-small-screen (width >= 360px);
@custom-media --only-medium-screen (width >= 900px)
```
### oproepen
```
    font-size: var(--fontBig);

  @media (--only-medium-screen) {
    background-image: none;
  }
}
```

## Importeren
```
@import './css/components/header.css';
```

### berekeningen
```
padding: calc(var(--spacerSmall) / 2.5) calc(var(--spacerSmall) * 1);
```

### nesten
```
.h1-like {
  font-size: var(--fontBig);
  display: block;

  &.h1-like::after {
    content: 'ssd';
  }
}
```

# JS
## ImportCSS
```
import './style.css';
```

## ImportJson
```
import data from './assets/data/coffees.json';

<!--  -->

  plantBasedCoffees = data.coffees.filter(coffee => coffee.plantbased === true);
  showCoffees(plantBasedCoffees);
```

## FindId
```
const inorderCoffee = findOrderByCoffeeId(coffee.id);

<!--  -->

const findOrderByCoffeeId = id => {
    return orders.find(order => order.coffee.id === id);
  };
```

## HandleClick 
```
const clickedCoffee = coffees.find(coffee => coffee.id === parseInt(e.currentTarget.dataset.id));
    addToOrder(clickedCoffee);
```


## IfAdd
```
if (inorderCoffee) {
      inorderCoffee.amount ++;
    } else {
      orders.push({
        amount: 1,
        id: coffee
      });
    }

    <!--  -->

    if (orders.length > 0) {
      // Hide empty state & show orders instead
      document.querySelector(`.orders__wrapper`).classList.remove(`hide`);
      document.querySelector(`.emptystate`).classList.add(`hide`);

      const $orders = document.querySelector(`.orders`);
      $orders.innerHTML = ``;
      orders.forEach(order => {
        const $li = createOrder(order);
        $orders.appendChild($li);
      });
    } else {
      // Show empty state
      document.querySelector(`.orders__wrapper`).classList.add(`hide`);
      document.querySelector(`.emptystate`).classList.remove(`hide`);
    }
```

## DataSet
```
$li.dataset.id = coffee.id;

<!--  -->

const clickedCoffee = plantBasedCoffees.find(coffee => coffee.id === parseInt(e.currentTarget.dataset.id));
addToOrder(clickedCoffee);
```

## RemoveId
```
const coffeeId = parseInt(e.currentTarget.parentElement.dataset.id);
  orders = orders.filter(order => {
  return coffeeId !== order.id.id;
});
```

## SQLToJson 
```
const $value = document.querySelector(`.input--filter`);
$value.addEventListener(`keyup`, handleSubmitFilterForm);

<!--  -->

const handleSubmitFilterForm = e => {
    console.log();
    e.preventDefault();
    const qs = new URLSearchParams([
      ...new FormData($filterForm).entries()
    ]).toString();
    fetch(`${$filterForm.getAttribute('action')}?${qs}`, {
      headers: new Headers({
        Accept: `application/json`
      }),
      method: 'get'
    })
      .then(r => r.json())
      .then(data => handleLoadPlayers(data));
    window.history.pushState(
      {},
      '',
      `${window.location.href.split('?')[0]}?${qs}`
    );
  };
```

## calculateTotal
```
const total = orders.reduce((total, order) => {
  return total + order.id.prices.medium * order.amount;
}, 0);
document.querySelector(`.total__price span`).textContent = total;
```
