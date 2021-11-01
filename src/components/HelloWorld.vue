<script setup lang="ts">
import { ref, reactive } from 'vue'
import { Field, Form, ErrorMessage } from 'vee-validate';

defineProps<{ msg: string }>();

function isRequired(value: any) {
  if (value && value.trim()) {
    return true;
  }

  return 'This is required';
}

function submit(e: any) {
  console.log(e)
}

</script>

<template>
  <h1>{{ msg }}</h1>
  <section id="test-drive" class="container js-tracking" data-gtm-code="viewtestdrive">
    <div class="block">
      <div class="title">
        <h2 class="title-main">表單</h2>
        <h3 class="title-sub" style="letter-spacing: 5px;">TEST DRIVE</h3>
      </div>
      <div class="row">
        <div class="col-sm-4 col-mdst-12 col-mdt-10 push-mdt-1">
          <Form @submit.prevent="submit">
            <Field name="field" :rules="isRequired" />
            <ErrorMessage name="field" />
            <button>Submit</button>
          </Form>
        </div>
      </div>
    </div>
  </section>
  
</template>

<style lang="scss" scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
