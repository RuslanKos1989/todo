<template>
    <div>
        <textarea
            class="input"
            :class="classes"
            :placeholder="placeholder"
            :type="type"
            :rows="rows"
            :value="value"
            @input="set"
            @focus="focus"
        >
        <slot />
        </textarea>
    </div>
</template>

<script>
    export default {
        name: 'Textarea',
        components: {

        },
        props: {
            value: {
                type: [Number, String],
                default: '',
            },
            placeholder: {
                type: String,
                default: '',
            },
            rows: {
                type: Number,
                default: 4,
            },
            type: {
                type: String,
                default: 'textarea',
            },
        },
        computed: {
            classes() {
                const current = ['input-textarea'];
                return current;
            },
        },
        methods: {
            set(e) {
                const value = e.target.value || '';
                this.$emit('input', value.toString());
            },
            focus(e) {
                this.$emit('focus', e);
            },
        },
    };
</script>

<style lang="scss">
    @import 'style';
</style>
