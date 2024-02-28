<template>
    <div>
        <button v-on="$listeners">
           <slot></slot>
        </button>

    </div>
</template>

<script>

export default{
}
</script>