<template>
    <div class="description">
        <p>
            {{todo.description}}
        </p>
    </div>
</template>

<script>
export default {
    name: "Description",
    props: ["todo"],
 
}
</script>

<style scoped>
    .description{

        background: #fff;
        margin: 5px;
        border-bottom: 1px #1A3E7A solid;

    }

</style>