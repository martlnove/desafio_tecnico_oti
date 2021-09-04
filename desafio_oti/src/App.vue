<template>
  <div>
    <h1>{{titulo}}</h1>
    <ul>
      <li v-for="produto of produtos">
        <img :src="produto.url" :alt="produto.titulo">
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return{
      titulo: 'Eletrodomesticos',
      produtos: [
        {
          url: 'https://brastemp.vtexassets.com/arquivos/ids/213732/Geladeira-BRE80AK-Frontal.jpg?v=637298140570900000',
          titulo: 'Geladeira'
        },
        {
          url: 'https://m.media-amazon.com/images/I/81m5hJSkwiL._AC_SY679_.jpg',
          titulo: 'Liquidificador'
        },
        {
          url: 'https://www.casasbahia-imagens.com.br/html/conteudo-produto/73/50004211/imagens/batedeira_2_.png',
          titulo: 'Batedeira'
        },
        {
          url: 'https://http2.mlstatic.com/D_NQ_NP_813885-MLA31454776804_072019-O.jpg',
          titulo: 'Microondas'
        },
        {
          url: 'https://novomundo.vteximg.com.br/arquivos/ids/1617816-500-500/fogao-5-bocas-de-piso-atlas-acendimento-automatico-tripla-chama-preto-tropical-glass-19-bivolt-58683-0.jpg?v=636994036049930000',
          titulo: 'Fogão'
        }

      ]
    }
  }
}
</script>

<style>

</style>
