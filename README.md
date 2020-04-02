<! DOCTYPE html >
< html >
  < cabeza >
    < meta  charset = " utf-8 " >

    < título > Nuestros superhéroes </ título >

    < link  href = " https://fonts.googleapis.com/css?family=Faster+One " rel = " stylesheet " >
    < link  rel = " stylesheet " href = " style.css " >
  </ cabeza >

  < cuerpo >

      < encabezado >

      </ header >

      < sección >

      </ sección >

    < guión >
    const  encabezado  =  documento . querySelector ( 'encabezado' ) ;
     sección  const =  documento . querySelector ( 'sección' ) ;

    let  requestURL  =  'https://mdn.github.io/learning-area/javascript/oojs/json/superheroes.json' ;
    let  request  =  new  XMLHttpRequest ( ) ;
    solicitud . abierto ( 'GET' ,  requestURL ) ;
    solicitud . responseType  =  'json' ;
    solicitud . enviar ( ) ;

    solicitud . onload  =  function ( )  {
      const  superHeroes  =  solicitud . la respuesta ;
      populateHeader ( superhéroes ) ;
      showHeroes ( superhéroes ) ;
    }

    función  populateHeader ( jsonObj )  {
      const  myH1  =  documento . createElement ( 'h1' ) ;
      myH1 . textContent  =  jsonObj [ 'squadName' ] ;
      cabecera . appendChild ( myH1 ) ;

      const  myPara  =  documento . createElement ( 'p' ) ;
      myPara . textContent  =  'Ciudad natal:'  +  jsonObj [ 'homeTown' ]  +  '// Formado:'  +  jsonObj [ 'formado' ] ;
      cabecera . appendChild ( myPara ) ;
    }

    función  showHeroes ( jsonObj )  {
      const  heroes  =  jsonObj [ 'miembros' ] ;

      for ( let  i  =  0 ;  i  <  heroes . length ;  i ++ )  {
        const  myArticle  =  documento . createElement ( 'artículo' ) ;
        const  myH2  =  documento . createElement ( 'h2' ) ;
        const  myPara1  =  documento . createElement ( 'p' ) ;
        const  myPara2  =  documento . createElement ( 'p' ) ;
        const  myPara3  =  documento . createElement ( 'p' ) ;
        const  myList  =  documento . createElement ( 'ul' ) ;

        myH2 . textContent  =  héroes [ i ] . nombrar ;
        myPara1 . textContent  =  'Identidad secreta:'  +  héroes [ i ] . identidad secreta ;
        myPara2 . textContent  =  'Edad:'  +  héroes [ i ] . edad ;
        myPara3 . textContent  =  'Superpoderes:' ;

        const  superPowers  =  héroes [ i ] . poderes ;
        for ( let  j  =  0 ;  j  <  superPowers . length ;  j ++ )  {
          const  listItem  =  documento . createElement ( 'li' ) ;
          listItem . textContent  =  superPowers [ j ] ;
          myList . appendChild ( listItem ) ;
        }

        myArticle . appendChild ( myH2 ) ;
        myArticle . appendChild ( myPara1 ) ;
        myArticle . appendChild ( myPara2 ) ;
        myArticle . appendChild ( myPara3 ) ;
        myArticle . appendChild ( myList ) ;

        sección . appendChild ( myArticle ) ;
      }
    }

    </ script >
  </ cuerpo >
</ html >                
