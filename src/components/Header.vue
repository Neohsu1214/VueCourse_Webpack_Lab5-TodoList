<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quote Added</h3>
            <!-- 以下為bootstrap的 proressbar 宣告 -->
            <div class="progress">
                <div class="progress">
                    <div class="progress-bar" role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100"
                    :style="{width: (quoteCount/maxQuotes) * 100 + '%' }">
                    <!-- 還記得 :style 是用來動態指定 style 內容的用法嗎？ -->
                        {{ quoteCount }} / {{ maxQuotes }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    // 承接由parent傳進來的參數
    props: ['quoteCount', 'maxQuotes']
}
</script>
<style>
    
</style>