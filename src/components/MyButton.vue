<template>
    <button @click="onClick" :class="`${asingarClase} ${asingarSize} ${isDisabled}`" :type="type"
        :disabled="disabled">{{ buttonText }}</button>
</template>

<script setup lang="ts">
//TODO: Consigna
// El componente debe: 
// -Poder habilitarse, deshabilitarse
// -Cambiar su color
// -Cualquier atributo/mejora extra será apreciado.

import { computed } from 'vue';

type TIPO_BOTON = "button" | "submit" | "reset"
type TIPO_CLASE = "success" | "danger" | "warning"
type TIPO_SIZE = "sm" | "md" | "lg" | "xl"

const props = defineProps({
    buttonText: {
        type: String,
        required: true
    },
    disabled: {
        type: Boolean,
        default: false
    },
    type: {
        type: String as () => TIPO_BOTON,
        validator(value: string) {
            return ["button", "submit", "reset"].includes(value)
        },
        default: "button"
    },
    class: {
        type: String as () => TIPO_CLASE,


    },
    size: {
        type: String as () => TIPO_SIZE,
        default: "md"
    },
    onClick: {
        type: Function,
        default: () => { }
    }
})


//Propiedades computadas
const asingarSize = computed(() => {
    if (props.size) {
        return `${props.size}`
    } else {
        return ""
    }
})
const asingarClase = computed(() => {
    if (props.class) {
        return `boton ${props.class}`
    } else {
        return "boton"
    }
})

const isDisabled = computed(() => {
    if (props.disabled) {
        return `isDisabled`
    } else {
        return ""
    }
})

</script>

<style scoped>
/* Estilo general del botm */
.boton {
    border-radius: 4px;
    color: white;
    border: transparent;
    margin: 2px;
    background-color: black;
    box-shadow: 1px 1px 2px black;
}

.boton:hover {
    box-shadow: 2px 2px 4px black;
}

/* Color de los botnes segun clase */
.success {
    background-color: green;

}

.danger {
    background-color: red;

}

.warning {
    background-color: rgb(211, 211, 64);
}

/*  En caso de estar deshabilitado*/
.isDisabled {

    background-color: gray;
    color: rgb(179, 179, 179)
}

/* Tamaños de los botones */
.sm {
    padding: 4px 8px;
    font-size: small;

}

.md {
    padding: 5px 10px;
    font-size: medium;

}

.lg {
    padding: 10px 20px;
    font-size: large;

}

.xl {
    padding: 12px 24px;
    font-size: larger;

}
</style>