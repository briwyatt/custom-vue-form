<script>
export default {
    props: {
        value: Array,
        required: true
    },
    data() {
        return {
            localValue: this.value || [],
        };
    },
    watch: {
        value(value) {
            this.localValue = value || [];
        }
    },
    methods: {
        toggleChoice(chosenvalue) {
            if (this.localValue.includes(chosenvalue)) {
                this.localValue = this.localValue.filter((v) => v !== chosenvalue);
            } else {
                this.localValue.push(chosenvalue);
            }
            this.$emit('input', this.localValue);
        }
    },
}
</script>

<template>
    <div
    class="is-flex">
        <div 
            class="box content mx-2" 
            :class="{'is-chosen' : value.includes('value 1')}"
            @click="toggleChoice('value 1')"
        >
            <h3>Choice 1</h3>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
        </div>
        <div 
            class="box content mx-2" 
            :class="{'is-chosen' : value.includes('value 2')}"
            @click="toggleChoice('value 2')"
        >
            <h3>Choice 2</h3>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
        </div>
        <div
            class="box content mx-2" 
            :class="{'is-chosen' : value.includes('value 3')}"
            @click="toggleChoice('value 3')"
        >
            <h3>Choice 3</h3>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
        </div>
        {{ value }}
    </div>
</template>

<style>
.box {
   cursor: pointer;
}
.box.is-chosen {
    border: 2px solid orange;
}
</style>

