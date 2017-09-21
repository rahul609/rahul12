# rahul12

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="https://unpkg.com/tachyons@4.8.0/css/tachyons.min.css"/>
    
    <title>Document</title>
</head>
<body>
        <a class="f6 link dim ba bw2 ph3 pv2 ma5 dib black" href="#0">Add 1 Hero</a>

    <main class="mw6 center">
      </main>
    
<script>

let heroes = [
  {'name' : 'Prof. Xavier', 'twitter' : '@profx', 'pic' : 'http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0004.gif'},
  {'name' : 'Spiderman', 'twitter' : '@spidey', 'pic' : 'http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0008.gif'},  
  {'name' : 'Wolverine', 'pic' : 'http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0011.gif', 'twitter' : '@logan' }
];


let moreHeroes = [
   {'name' : 'Cyclops', 'twitter' : '@oneye', 'pic' : 'http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0005.gif'},
   {'name' : 'Storm', 'twitter' : '@rainsitpours', 'pic' : 'http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0007.gif'},
   {'name' : 'Phoenix', 'twitter' : '@jeangrey', 'pic' : 'http://www.animatedimages.org/data/media/450/animated-marvel-avatar-image-0016.gif'}
];


let main = document.querySelector('main');

function hardy(heroes) {
main.innerHTML = `${heroes.map( (hero, index) => `


    <article class="dt w-100 bb b--black-05 pb2 mt2" href="#0">
          <div class="dtc w2 w3-ns v-mid">
            <img src=${hero.pic} class="ba b--black-10 db br-100 w2 w3-ns h2 h3-ns"/>
          </div>
          <div class="dtc v-mid pl3">
            <h1 class="f6 f5-ns fw6 lh-title black mv0">${hero.name} </h1>
            <h2 class="f6 fw4 mt0 mb0 black-60">${hero.twitter}</h2>
          </div>
          <div class="dtc v-mid">
            <form class="w-100 tr">
              <button data-id=${index} class="f6 button-reset bg-white ba b--black-10 dim pointer pv1 black-60" type="submit">${hero.following ? 'Following' :'+Follow'}</button>
            </form>
          </div>
        </article>

`).join(``)}


    `;

    let butn_follow = Array.from(document.querySelectorAll('[data-id]'));
    butn_follow.map( butn => butn.addEventListener('click', function(e) {
    e.preventDefault();

    //if this particular hero has the following:true key/value, than delete that key/value.
    // else add it.
    
    
    
 }));
     


    
 

}



function* idMaker() {
  var index = 0;
  while (index < moreHeroes.length)
    yield moreHeroes[index++];
}

var gen = idMaker();


let button_add1Hero = document.querySelector('a');
button_add1Hero.addEventListener('click' , function(event){
    event.preventDefault();
    let obj = gen.next();
    obj.done ? console.warn('no more heroes') : heroes.push(obj.value);
    hardy(heroes);

})


hardy(heroes);

       
</script>


</body>
</html>

