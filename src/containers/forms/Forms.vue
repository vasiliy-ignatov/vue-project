<template>
	<div>
		<root-component :title="'1. Текстовый инпут'">
			<input type="text" v-model.lazy="name">
			<p>{{ name }}</p>
		</root-component>

		<root-component :title="'2. Текстарея'">
			<textarea v-model="textarea"></textarea>
			<p>{{ textarea }}</p>
		</root-component>

		<root-component :title="'3. Чекбоксы'">
			<app-checkboxes></app-checkboxes>
		</root-component>

		<root-component :title="'4. Радио кнопки'">
			<app-radio></app-radio>
		</root-component>

		<root-component :title="'5. Селекты'">
			<app-select></app-select>
		</root-component>

		<root-component :title="'6. Числовой модификатор v-model'">
			<app-intmod></app-intmod>
		</root-component>

		<root-component :title="'7. Кастомный v-model'">
			<app-control v-model="switched"></app-control>
			<p v-if="switched">Component is enabled</p>
			<p v-else>Component is disabled</p>
		</root-component>

		<root-component :title="'8. Валидация форм с vuelidate'">
			<app-validate></app-validate>
		</root-component>

		<root-component :title="'9. Кастомная валидация форм с vuelidate(uniqEmail)'">
			<app-custom-validate></app-custom-validate>
		</root-component>

		<root-component :title="'10. Отправка формы'">
			<app-form-submit></app-form-submit>
		</root-component>
	</div>
</template>

<script>
import Component from './../../hoc/Component.vue'
import CheckboxesVue from './components/Checkboxes.vue'
import Radio from './components/Radio.vue'
import Select from './components/Select.vue'
import Intmod from './components/Intmod.vue'
import Control from './components/Control.vue'
import Validate from './components/Validate.vue'
import CustomValidate from './components/CustomValidate.vue'
import FormSubmit from './components/FormSubmit.vue'


export default {
	data() {
		return {
			name: 'Initial state',
			textarea: 'I am initial text',
			switched: false
		}
	},
	components: {
		rootComponent: Component,
		appCheckboxes: CheckboxesVue,
		appRadio: Radio,
		appSelect: Select,
		appIntmod: Intmod,
		appControl: Control,
		appValidate: Validate,
		appCustomValidate: CustomValidate,
		appFormSubmit: FormSubmit
	}
}
</script>

<style scoped>
	textarea {
		width: 400px;
		height: 100px;
	}

	p {
		white-space: pre;
	}
</style>
