<template>
    <div class="modal-view-input">
        <title>{{ name }}</title>
        <input
            v-validate="validation"
            :name="name"
            :type="type"
            v-bind="$attrs"
            @input="$emit('input', $event.target.value)"
        />
        <span class="error">{{ errors.first(name) }}</span>
    </div>
</template>

<script>
export default {
    props: {
        name: {
            type: String,
            required: true
        },
        validation: {
            type: String,
            default: ''
        },
        type: {
            type: String,
            default: 'text'
        }
    }
}
</script>

<style lang="scss" src="@/components/ModalViewInput.scss" scoped></style>
