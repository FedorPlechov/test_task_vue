<template>
  <TheHeader @goTo="goTo($event)"/>
  <keep-alive>
    <component :is="page"
               :form="form"
               @saveChildren="setChildrenInform($event)"
               @saveNameAndAge="setNameAndAge($event)">
    </component>
  </keep-alive>
  <TheFooter/>
</template>

<script>
import TheFooter from "@/components/layouts/TheFooter";
import Form from "./form/Form";
import TheHeader from "@/components/layouts/TheHeader";
import ThePreview from "@/components/personalData/preview/ThePreview";


export default {
  name: "ThePersonalData",
  components: {
    TheHeader,
    ThePreview,
    Form,
    TheFooter
  },
  data() {
    return {
      form: {
        name: '',
        age: '',
        children: []
      },
      page: 'Form'
    }
  },
  methods: {
    setNameAndAge(payload) {
      this.form.name = payload.name;
      this.form.age = payload.age;
    },
    setChildrenInform(children) {
      this.form.children = children;
    },
    goTo(page) {
      this.page = page;
    }
  }
}
</script>

<style scoped>

</style>
