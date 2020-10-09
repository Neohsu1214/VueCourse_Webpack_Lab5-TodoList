<template>
    <div class="row">
        <form>
            <!-- 一狗票class定義都是bootstrap的用於RWD，詳見bootstrap定義文件 -->
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Quote</label>
                <textarea class="form-control" rows="3" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
                <!-- 若 click事件後，不加上prevent，則會因為預設動作是 reload 而使得整個頁面重繪 -->
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data: function() {
            return {
                quote: ''
            }
        },
        methods: {
            createNew: function() { // 也可以寫成 create() {}
                // 將新增的 quote 資料送給 parent component，並清除掉
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style>
    
</style>
