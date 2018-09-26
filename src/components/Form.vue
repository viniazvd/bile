<template>
  <div id="app">
    <form id="form">
      <c-input
        label="Razão social"
        name="name"
        :validation="$hasError('name', 'form')"
        v-model="form.name"
      />

      <c-input
        label="E-mail"
        name="email"
        :validation="$hasError('email', 'form')"
        v-model="form.email"
      />

      <c-input
        label="Cnpj"
        name="registry_code"
        :validation="$hasError('registry_code', 'form')"
        v-model="form.registry_code"
      />

      <c-input
        label="Telefone"
        name="phone"
        :validation="$hasError('phone', 'form')"
        v-model="form.phone"
      />

      <c-input
        label="Cep"
        name="zipcode"
        :validation="$hasError('zipcode', 'form')"
        v-model="form.zipcode"
      />

      <c-input
        label="Número"
        name="number"
        :validation="$hasError('number', 'form')"
        v-model="form.number"
      />

      <c-input
        label="Complemento"
        name="additional_details"
        v-model="form.additional_details"
      />

      <c-input
        label="Bairro"
        name="neighborhood"
        :validation="$hasError('neighborhood', 'form')"
        v-model="form.neighborhood"
      />

      <c-input
        label="Cidade"
        name="city"
        :validation="$hasError('city', 'form')"
        v-model="form.city"
      />

      <c-input
        label="Estado"
        name="state"
        :validation="$hasError('state', 'form')"
        v-model="form.state"
      />

      <c-input
        label="Observações"
        name="description"
        v-model="form.description"
      />
    </form>
  </div>
</template>

<script>
import CInput from './Base/CInput'
import CInputContainer from './Base/CInputContainer'

import { formSetup } from 'vue-coe-validator'

const required = { required: true }

export default {
  name: 'init-form',

  components: { CInput, CInputContainer },

  mixins: [ formSetup ],

  data () {
    return {
      form: {
        name: '',
        email: '',
        registry_code: '',
        phone: '',
        zipcode: '',
        number: '',
        additional_details: '',
        neighborhood: '',
        city: '',
        state: '',
        description: ''
      }
    }
  },

  validation: {
    form: {
      name: required,
      email: {
        required: true,
        pattern: /^[A-Z0-9_'%=+!`#~$*?^{}&|-]+([.][A-Z0-9_'%=+!`#~$*?^{}&|-]+)*@[A-Z0-9-]+(\.[A-Z0-9-]+)+$/i
      },
      registry_code: required,
      phone: required,
      zipcode: required,
      number: required,
      neighborhood: required,
      city: required,
      state: required
    }
  }
}
</script>
