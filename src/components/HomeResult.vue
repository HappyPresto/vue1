<template>
<div>
{{show}}
<table class="tableResult">
    <tbody>
        <tr v-for="(item, index) in info" :key="index">
            <td>{{item.title}}</td>
            <td>{{item.result.value}}</td>
        </tr>
    </tbody>
</table>
</div>
</template>

<script>
export default {
    props: ["info", "show"]
}
</script>