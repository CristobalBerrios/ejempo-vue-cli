<template>
  <section>
    <v-data-table
    :headers="headers"
    :items="usuarios"
    class="elevation-10">
      <template slot="items" slot-scope="props">
        <td>{{ props.item.firstname }}</td>
        <td>{{ props.item.lastname }}</td>
        <td>{{ props.item.age }}</td>
      </template>
    </v-data-table>
    <v-btn color="red" :disabled="disabled" class="yellow--text">Success</v-btn>
    <input v-model="texto">
</section>
</template>

<script>
export default {
  data () {
    return {
      texto: '',
      headers: [
        { text: 'First Name', value: 'firstname' },
        { text: 'Last Name', value: 'lastname' },
        { text: 'Age', value: 'age' }
      ],
      usuarios: [
        {
          firstname: 'Jill',
          lastname: 'Smith',
          age: 50
        },
        {
          firstname: 'Eve',
          lastname: 'Jackson',
          age: 100
        }
      ]
    }
  },
  props: ['title'],
  methods: {
    mostrarAlert () {
      alert('holaa')
    }
  },
  computed: {
    disabled () {
      return !(this.texto === 'hola')
    }
  }
}
</script>

