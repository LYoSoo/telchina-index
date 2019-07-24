<template>
    <div class="main">
        <el-row>
            <el-col :span="18" :offset="4">
                <img class="img-item" src="https://i.loli.net/2019/07/11/5d26f667f026494679.jpg">
                <img class="img-item" src="https://i.loli.net/2019/07/11/5d26f6680c04462856.jpg">
                <img class="img-item" src="https://i.loli.net/2019/07/11/5d26f6681a9d510855.jpg">
            </el-col>
        </el-row>
    </div>
</template>

<script>
export default {
    name: "Contact"
}
</script>

<style lang="less" scoped>
    .main{
        width: 100%;
        height: 80px;
        background-color: rgb(65,120,190);
        .img-item{
            width: 40px;
            height: 40px;
            margin-top: 20px;
            display: inline-block;
            margin-right: 10px;
        }
    }
</style>
