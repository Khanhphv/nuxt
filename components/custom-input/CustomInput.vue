<template lang="pug">
	b-form-group(:label="label")
		b-form-input(:type="type" :name="name")
</template>
<script lang="ts">
import Vue from 'vue'
import { Component, Prop } from "nuxt-property-decorator"

enum INPUT_TYPE {
	text = "text",
	email = "email"
}

@Component
class CustomInput extends Vue {
	@Prop() name!:string
	@Prop() type!:INPUT_TYPE
	@Prop() label!:string
}

export default CustomInput
</script>