<template>
<div style="justify:center">
  <v-row>
    <v-col style="background-color:aquamarine; border-radius:50px " 
    class="pa-md-5 mr-md-1 ">
      <h2>PREU</h2>
        <v-text-field
          outlined
          rounded
          clearable
          label="Preu"
          v-model="preu"
          type="number"
          prepend-inner-icon="mdi-email"
          maxlength="3"
          single-line
          counter
          style="max-width:50%"
        ></v-text-field>
      <h2>COST</h2>
      <v-text-field
        outlined
        rounded
        clearable
        label="Cost"
        v-model="cost"
        type="number"
        prepend-inner-icon="mdi-email"
        maxlength="3"
        single-line
        counter
        style="max-width:50%"
      ></v-text-field>
    </v-col>
    <v-col 
      style="background-color:aquamarine; border-radius:50px " 
      class="pa-md-5 mr-md-1" cols="6">
      <p>"El client paga <strong>{{preu}}</strong> euros per un producte.</p> <br>
      <p>L'estat es queda impostos per valor de <strong>{{ iva }}</strong> euros (21% d'IVA).</p>
      <p>El producte ens ha costat <strong>{{cost}}</strong></p>
      <p>Per tant, el marge que et qurda a tu com a vendor és de <strong>{{marge}}</strong> euros.</p>
    </v-col>
  </v-row>
</div>
 
</template>

<script>
export default {
  data(){
    return{
      preu:50,
      cost:25,
    }
  },
  computed:{
    marge(){
    return parseInt(this.preu) - (this.iva + parseInt(this.cost))
    },

    iva(){
        return this.preu * 0.21
    }
  }
}
</script>
