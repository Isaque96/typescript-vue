<template>
  <div>
    <h1>Contador (Classe)</h1>
    <h2>{{ valor }}</h2>
    <h3>{{ parOuImpar }}</h3>
    <button @click="setValor(-1)">Dec</button>
    <button @click="setValor(1)">Inc</button>
  </div>
</template>

<script lang="ts">
import { Options, Vue, prop } from "vue-class-component";

class Props {
  valorInicial = prop({
    type: Number,
    default: 0,
    required: true,
  });
}

@Options({})
export default class ContadorClasse extends Vue.with(Props) {
  valor = this.valorInicial;

  public setValor(delta: number) {
    this.valor += delta;
  }

  public getParOuImpar(): string {
    return this.valor % 2 === 0 ? "Par" : "Impar";
  }

  public get parOuImpar(): string {
    return this.valor % 2 === 0 ? "Par" : "Impar";
  }
}
</script>

<style></style>
