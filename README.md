# aula-8-da-alura
super Trunfo


https://codepen.io/chritianegozza/pen/VwPbNoO


![image](https://user-images.githubusercontent.com/72118415/113517105-853b9c80-9554-11eb-8c70-6ecb4acaad49.png)



html

<html>

<head>
    <title>
        Imersão Dev - Aula 08
    </title>
</head>

<body>
    <div class="container">
        <img src="https://www.alura.com.br/assets/img/imersoes/dev-2021/logo-imersao-super-trunfo.png" class="page-logo"
            alt="">
        <h1 class="page-title">Super Trunfo</h1>
        <button onclick="sortearCarta()" id="btnSortear">Sortear carta</button>
        <form id="form">
            <h2>Escolha o seu atributo</h2>
            <div class="wrapper">
                <div>
                    <div id="carta-jogador">
                        <img src="https://www.alura.com.br/assets/img/imersoes/dev-2021/card-super-trunfo-transparent-ajustado.png"
                            style=" width: inherit; height: inherit; position: absolute;">
                        <h3></h3>
                    </div>
                </div>
                <div>
                    <div id="carta-maquina" class="carta"><img
                            src="https://www.alura.com.br/assets/img/imersoes/dev-2021/card-super-trunfo-transparent-ajustado.png"
                            style=" width: inherit; height: inherit; position: absolute;"></div>
                </div>
            </div>
            <button class="button-jogar" type="button" id="btnJogar" onclick="jogar()" disabled="false">Jogar</button>
            <div id="resultado"></div>
        </form>
    </div>
</body>


   
  
</html>




css


body {
    font-family: 'Roboto Mono', monospace;
    min-height: 654px;
    background-image: url('https://s2.glbimg.com/2C0hMRuCY_7NfDPjby4_Bjmq8Nc=/e.glbimg.com/og/ed/f/original/2018/03/22/avengers-infinity-war-official-poster-2018-4o.jpg');
    background-color: #000000;
    background-size: cover;
    background-position: center top;
    background-repeat: no-repeat;
    padding-bottom: 20vh;
}

.container {
    text-align: center;
    padding: 30px;
}

.page-title {
    color: #ffffff;
    margin: 5px 0;
}

button, .button-jogar {
    padding: .8rem 1.5rem;
    margin: 1rem 0;
    border-radius: 5px;
    border: none;
    font-size: 1rem;
}

h2 {
    color: white;
}

#carta-jogador, #carta-maquina {
    width: 360px;
    height: 500px;
    overflow: auto;
    border-radius: 10px;
    margin-bottom: 20px;
    margin: 0 auto;
    display: flex;
    align-items: flex-end;
    position: relative;
    background-size: 350px 300px;
    background-repeat: no-repeat;
    background-position-x: 5px;
    background-position-y: 10px;
    border-radius: 33px;
}

#carta-jogador h3 {
    text-align: center;
}

.carta-imagem {
    border: 1px solid black;
    height: 100px;
    margin: 10px;
}

.carta-imagem img {
    width: 60%;
    height: 60%;
}

.carta-status {
    height: 160px;
    margin: 2rem;
    color: white;
    z-index: 2;
}

.carta-status input {
    margin: 20px 10px;
}

.resultado-final {
    color: white;
    font-size: 2rem;
    text-transform: uppercase;
    font-weigth: bolder;
    padding: 1rem;
    border: 2px solid black;
    background-color: black;
}

.--spacing {
    margin-left: 2.5rem;
}

form {
    display: flex;
    flex-direction: column;
}

.wrapper {
    display: flex;
    justify-content: space-between;
    width: 100%;
}

.carta-subtitle {
    z-index: 2;
    position: absolute;
    top: 16px;
    left: 37px;
    font-weight: 800;
    text-transform: uppercase;
}

#cartas {
    width: 100%;
    display: flex;
    justify-content: space-between;
}

.carta-status p {
    margin-bottom: 2rem;
}





js  


var cartaChristiane = {
  nome: "Thor",
  imagem:"https://cdn.ome.lt/pfIcbIk870YITAzNsEQ2Tx8kdlA=/1200x630/smart/extras/conteudos/thor-love-5.jpg",
  atributos:{ 
  ataque:80,
  defesa:60,
  magia:90
  }
}

var cartaArthur = {
  nome: "Homem Aranha",
  imagem:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTPOZ3Jd6cPfwq-kv9jnB8LEg95WhRHDVtcgg&usqp=CAU",
  atributos: {
  ataque:80, 
  defesa:65,
  magia:60
}
   }

var cartaAlex = {
  nome: "Homem de Ferro",
  imagem:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSGKJaG94gKfqvjaeYebES0loDS_uImMaru1Q&usqp=CAU",
   atributos: {
  ataque:90, 
  defesa:65,
  magia:68
}
   }

var cartaIsabella = {
  nome: "Viuva negra",
  imagem:"https://files.nsctotal.com.br/s3fs-public/styles/itapema_blog_post_header/public/2019-07/VN003.jpg?2u4baFQ6jFSzBsibg3hCB5Ce3us8vNbK&itok=8Ie-DBXO",
  atributos:{ 
  ataque:88,
  defesa:70,
  magia:90
  }
}

var cartaYasmin = {
  nome: "capitã Marvel",
  imagem:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQGO-NcF2g0EKppmElNs4Exrsg4JOLmmxKTdw&usqp=CAU",
  atributos: {
  ataque:88, 
  defesa:75,
  magia:80
}
   }

var cartaMarcela = {
  nome: "Feiticeira Escarlate",
  imagem:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQS3cPMwzgeB3j_66vFOcf4BWKQxV6YWIW2cg&usqp=CAU",
  atributos: {
  ataque:90, 
  defesa:80,
  magia:90
}
   }

var cartaMaquina
var cartaJogador
var cartas = [cartaChristiane, cartaArthur, cartaAlex, cartaIsabella, cartaYasmin, cartaMarcela]
             // 0              1             2            3             4               5


function sortearCarta() {
    var numeroCartaMaquina = parseInt(Math.random() * 6)
    cartaMaquina = cartas[numeroCartaMaquina]

    var numeroCartaJogador = parseInt(Math.random() * 6)
    while (numeroCartaJogador == numeroCartaMaquina) {
        numeroCartaJogador = parseInt(Math.random() * 6)
    }
    cartaJogador = cartas[numeroCartaJogador]
    console.log(cartaJogador)

    document.getElementById('btnSortear').disabled = true
    document.getElementById('btnJogar').disabled = false

    exibeCartaJogador()
}


function exibeCartaJogador() {
    var divCartaJogador = document.getElementById("carta-jogador")
    var moldura = '<img src="https://www.alura.com.br/assets/img/imersoes/dev-2021/card-super-trunfo-transparent.png" style=" width: inherit; height: inherit; position: absolute;">';
    divCartaJogador.style.backgroundImage = `url(${cartaJogador.imagem})`
    var nome = `<p class="carta-subtitle">${cartaJogador.nome}</p>`
    var opcoesTexto = ""

    for (var atributo in cartaJogador.atributos) {
        opcoesTexto += "<input type='radio' name='atributo' value='" + atributo + "'>" + atributo + " " + cartaJogador.atributos[atributo] + "<br>"
    }

    var html = "<div id='opcoes' class='carta-status'>"

    divCartaJogador.innerHTML = moldura + nome + html + opcoesTexto + '</div>'
}

function obtemAtributoSelecionado() {
    var radioAtributo = document.getElementsByName('atributo')
    for (var i = 0; i < radioAtributo.length; i++) {
        if (radioAtributo[i].checked) {
            return radioAtributo[i].value
        }
    }
}

function jogar() {
    var divResultado = document.getElementById("resultado")
    var atributoSelecionado = obtemAtributoSelecionado()

    if (cartaJogador.atributos[atributoSelecionado] > cartaMaquina.atributos[atributoSelecionado]) {
        htmlResultado = '<p class="resultado-final">Venceu</p>'
    } else if (cartaJogador.atributos[atributoSelecionado] < cartaMaquina.atributos[atributoSelecionado]) {
        htmlResultado = '<p class="resultado-final">Perdeu</p>'
    } else {
        htmlResultado = '<p class="resultado-final">Empatou</p>'
    }

    divResultado.innerHTML = htmlResultado
    exibeCartaMaquina()
}

function exibeCartaMaquina() {
    var divCartaMaquina = document.getElementById("carta-maquina")
    var moldura = '<img src="https://www.alura.com.br/assets/img/imersoes/dev-2021/card-super-trunfo-transparent.png" style=" width: inherit; height: inherit; position: absolute;">';
    divCartaMaquina.style.backgroundImage = `url(${cartaMaquina.imagem})`
    var nome = `<p class="carta-subtitle">${cartaMaquina.nome}</p>`
    var opcoesTexto = ""

    for (var atributo in cartaMaquina.atributos) {
        console.log(atributo)
        opcoesTexto += "<p type='text' name='atributo' value='" + atributo + "'>" + atributo + " " + cartaMaquina.atributos[atributo] + "<br>"
    }

    var html = "<div id='opcoes' class='carta-status --spacing'>"

    divCartaMaquina.innerHTML = moldura + nome + html + opcoesTexto + '</div>'
}


