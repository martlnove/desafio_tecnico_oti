<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Desafio Técnico OTI Software</a>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
           <form class="d-flex">
            <input class="form-control me-2" type="search" v-on:input="busca = $event.target.value" placeholder="Encontre seu produto!" aria-label="Search">
           </form>
         </div>
      </div>
    </nav>
    <div class="alert alert-dark" role="alert">
      <h1 class="alert-heading">{{titulo}}</h1>
      <hr>
      <p>{{mensagem}}</p>
    </div>
    <ul class="text-center lista">
      <li class="rounded lista-produto" v-for="produto of buscaProdutos">
        <div class="painel">
          <h2 class="painel-titulo">{{produto.titulo}}</h2>
          <img class="img-fluid size" :src="produto.url" :alt="produto.titulo">
        </div>
      </li>
    </ul>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Desafio Técnico Software - OTI Copyright © 2017 OTI Software</a>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return{
      titulo: 'Nossos Produtos',
      mensagem: 'Aqui você confere todos os nossos eletrodomésticos para sua residência',
      produtos: [
        {
          id: 'prodgel',
          url: 'https://consul.vtexassets.com/arquivos/ids/218419-800-auto?width=800&height=auto&aspect=true',
          titulo: 'Geladeira',
        },
        {
          id: 'prodliqui',
          url: 'https://www.extra-imagens.com.br/Control/ArquivoExibir.aspx?IdArquivo=149305041',
          titulo: 'Liquidificador'
        },
        {
          id: 'prodbat',
          url: 'https://www.casasbahia-imagens.com.br/html/conteudo-produto/73/50004211/imagens/batedeira_2_.png',
          titulo: 'Batedeira'
        },
        {
          id: 'prodmicro',
          url: 'https://d296pbmv9m7g8v.cloudfront.net/Custom/Content/Products/99/39/993960_microondas-panasonic-style-nnst67hs-900w-32-litros-10003980_m53_637475373249592555',
          titulo: 'Microondas'
        },
        {
          id: 'prodofog',
          url: 'https://novomundo.vteximg.com.br/arquivos/ids/1617816-500-500/fogao-5-bocas-de-piso-atlas-acendimento-automatico-tripla-chama-preto-tropical-glass-19-bivolt-58683-0.jpg?v=636994036049930000',
          titulo: 'Fogão'
        },
        {
          id: 'prodair',
          url: 'https://images-americanas.b2w.io/produtos/01/00/img/134230/1/134230135_1GG.jpg',
          titulo: 'Air Fryer'
        },
        {
          id: 'prodtorra',
          url: 'http://philco.vteximg.com.br/arquivos/ids/175013/Torradeira-BTR01P_066201023--3-.jpg?v=637038018154730000',
          titulo: 'Torradeira'
        },
        {
          id: 'prodvent',
          url: 'https://a-static.mlcdn.com.br/618x463/ventilador-arno-40cm-turbo-force-vf49-vf49/gazinshop/8931/097736b9cdf3f254a28e9ca800790ecd.jpg',
          titulo: 'Ventilador'
        }
      ],
      busca: ''
    }
  },
  computed: {
    buscaProdutos(){
      if(this.busca){
        let exp = new RegExp(this.busca.trim(),'i');
        return this.produtos.filter(produto => exp.test(produto.titulo));
      }else{
        return this.produtos;
      }
    }
  }
}
</script>

<style>
.lista {
    list-style: none;
  }
.painel {
    padding: 0 auto;
    border: solid 2px grey;
    display: inline-block;
    margin: 5px;
    box-shadow: 5px 5px 10px grey;
    width: 300px;
    height: 100%;
    vertical-align: top;
    text-align: center;
  }

.painel .painel-titulo {
    color: #FFF;
    text-align: center;
    border: solid 2px;
    background: #003c86;
    margin: 0 0 15px 0;
    padding: 10px;
    text-transform: uppercase;
  }
.size{
  width:100%;
}
.lista .lista-produto {
    display: inline-block;
}
</style>
