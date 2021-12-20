<script>
import Card from './components/Card.vue'
import Form from './components/Form.vue'

export default {
  name: 'App',
  components: {
    Card, Form
  },
  data() {
    return {
      data: [
        {
          'category': 'Predveď 1',
          'mission': 'Predveď nám ako robí sob'
        },
        {
          'category': 'Prines 1',
          'mission': 'Prines vianočnú ozdobu, ktorú máš pri sebe najbližšie'
        },
        {
          'category': 'Vymysli 1',
          'mission': 'Vymysli tanček na Tichú noc (1.sloha)'
        },
        {
          'category': 'Odpovedz 1',
          'mission': 'Aký najšialenejší darček si dostal/la/kúpil/la alebo chcel/la dostať/kúpiť'
        },
        {
          'category': 'Prines 2',
          'mission': 'Prines niečo, bez čoho si nevieš predstaviť Vianoce'
        },
        {
          'category': 'Predveď 2',
          'mission': 'Predveď vianočný zhon'
        },
        {
          'category': 'Predveď 3',
          'mission': 'Predveď vianočnú pohodu'
        },
        {
          'category': 'Vymysli 2',
          'mission': 'Vymysli vinš, ktorý obsahuje tieto slová: Vianoce, ambasádori, stromček, vízia, sviečky, impakt'
        },
        {
          'category': 'Odpovedz 2',
          'mission': 'Aký koláč zmizne z vášho vianočného stola čo najskôr?'
        },
        {
          'category': 'Predveď 4',
          'mission': 'Zahmkaj vianočnú pieseň a my budeme hádať'
        },
        {
          'category': 'Odpovedz 3',
          'mission': 'Najväčší trapas počas Vianoc?'
        },
        {
          'category': 'Vymysli 3',
          'mission': 'Nakresli  na papier postavu/postavičku, ktorá sa ti spája s Vianocami a my budeme hádať'
        }
      ]
    }
  },
  methods: {
    add(data) {
      this.data.push({
        'category': data[0],
        'mission': data[1]
      })
    }
  },
}
</script>

<template>
  <main>
    <div class="cards">
        <Card v-for="(card, index) in data" :key="index" :category="card.category" :mission="card.mission" />
    </div>
    <Form @add="add($event)"></Form>
  </main>
</template>

<style>

</style>