<template>
  <div class="curso-main-container referencias">
    <BannerInterno
      icono="fas fa-book"
      titulo="Referencias bibliográficas"
    ></BannerInterno>
    <div class="container tarjeta tarjeta--blanca p-4 p-md-5 mb-5">
      <div v-for="ref in orderedData" :key="ref.link" class="referencias__item">
        <span v-html="ref.referencia"></span
        ><a v-if="ref.link" class="ms-1" :href="ref.link" target="_blank"
          ><span v-html="ref.link"></span
          ><i class="ms-1 fas fa-external-link-alt"></i
        ></a>
        <hr class="my-3" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Referencias',
  data: () => ({
    referencias: [
      {
        referencia:
          'Fernández, R., & García, M. (2021). <em>Mecánica y mantenimiento en maquinaria agrícola: Guía práctica para técnicos y agricultores</em>. Editorial Agrícola.',
        link: '',
      },
      {
        referencia:
          'García, R. (2023). <em>Mecanizado CNC y su Aplicación en la Industria.</em> Biblioteca SENA. ',
        link: 'https://biblioteca.sena.edu.co/',
      },
      {
        referencia:
          'García, T., & Rivas, L. (2016). <em>Mantenimiento preventivo y correctivo en equipos agrícolas.</em> Editorial de Tecnología Agrícola.',
        link: '',
      },
      {
        referencia:
          'González, M. (2015). <em>Lubricación y reducción de fricción en maquinaria de campo.</em> Editorial Ingeniería Sostenible.',
        link: '',
      },
      {
        referencia:
          'López, P., & Torres, F. (2020). <em>Conceptos avanzados de mecánica aplicada en el sector agrícola.</em> Ingeniería y Tecnología Agrícola.',
        link: '',
      },
      {
        referencia:
          'Maristas Huelva. (n.d.). <em>Arduino: Libro kit básico.<em> [Documento PDF]. ',
        link:
          'https://www.maristashuelva.es/webinfo/tecnologia/arduino/Libro_kit_Basico.pdf',
      },
      {
        referencia:
          'Martínez, J., & Díaz, C. (2019). <em>Ajustes y tolerancias en maquinaria agrícola pesada.</em> Ediciones Técnicas.',
        link: '',
      },
      {
        referencia:
          'Núñez, F. (2022). <em>Fundamentos de Electrotecnia.</em> [Video]. YouTube. ',
        link: 'https://www.youtube.com/c/AprenderElectricidad ',
      },
      {
        referencia:
          'Organización Internacional del Trabajo. (2024). <em>Big Data: conceptos y herramientas.</em> [Artículo]. OIT. ',
        link: 'https://www.oit.org/big_data_conceptos',
      },
      {
        referencia:
          'Ramírez, S. (2017). <em>Transferencia de energía y sistemas de transmisión en maquinaria agrícola.</em> Editorial Innovación en Agricultura.',
        link: '',
      },
      {
        referencia:
          'Rodríguez, A. (2022). <em>Introducción al Dibujo Técnico.</em> Universidad Abierta. ',
        link: 'https://www.universidadabierta.edu/dibujo_tecnico',
      },
      {
        referencia:
          'Salazar, J., & Pérez, M. (2014). <em>Métodos de unión y ensamblaje en equipos agrícolas.</em> Ediciones del Agro.',
        link: '',
      },
      {
        referencia:
          'Servicio Nacional de Aprendizaje – SENA. (2024). <em>Mecánica y Ajuste en Maquinaria Agrícola.</em> [Manual]. Repositorio SENA.',
        link: 'https://repositorio.sena.edu.co/handle/11404/4761',
      },
      {
        referencia:
          'Sistema de Bibliotecas SENA. (2024). <em>Metrología</em> - Módulo Básico. ',
        link: 'https://biblioteca.sena.edu.co/',
      },
      {
        referencia:
          'Smith, A., & Johnson, R. (2018). <em>Dinámica y estática para maquinaria industrial y agrícola.</em> Prensa de Ingeniería Aplicada.',
        link: '',
      },
      {
        referencia:
          'Tinkercad. (n.d.). <em>Circuitos DC y AC: Simulador en línea.</em> [Simulador en línea]. ',
        link: 'https://www.tinkercad.com/embed/g1Pvn5fI1mE',
      },
      {
        referencia:
          'YouTube. (n.d.). <em>¿Cómo funciona el transistor?</em> [Video].',
        link: 'https://www.youtube.com/watch?v=ljSdrYmdF44',
      },
      {
        referencia:
          'YouTube. (n.d.). <em> ¿Qué es un semiconductor?</em> [Video]. ',
        link: 'https://www.youtube.com/watch?v=fFVU7-kfPe8',
      },
      {
        referencia:
          'YouTube. (n.d.). <em> Diferencias entre corriente alterna y corriente directa.</em> [Video]. ',
        link: 'https://www.youtube.com/watch?v=BPaIiaoYkNY',
      },
      {
        referencia: 'YouTube. (n.d.). <em> Electrónica digital.</em> [Video]. ',
        link: ' https://www.youtube.com/watch?v=MPEHYhKQztQ',
      },
      {
        referencia:
          'YouTube. (n.d.). <em> TRANSISTORIZED! La Historia De: El Transistor.</em> [Video]. ',
        link: 'https://www.youtube.com/watch?v=f3IUVvJ2XgI&t=1899s',
      },
    ],
  }),
  computed: {
    orderedData() {
      return [...this.referencias].sort((a, b) => {
        const afl = this.quitarAcentos(a.referencia.split(' ')[0].toLowerCase())
        const bfl = this.quitarAcentos(b.referencia.split(' ')[0].toLowerCase())
        if (afl < bfl) return -1
        if (afl > bfl) return 1
        return 0
      })
    },
  },
  methods: {
    quitarAcentos(str) {
      return str.normalize('NFD').replace(/[\u0300-\u036f]/g, '')
    },
  },
}
</script>

<style lang="sass">
.referencias
  &__item
    &:last-child
      hr
        display: none
    a
      color: $blue
      text-decoration: underline
      overflow-wrap: break-word
</style>
