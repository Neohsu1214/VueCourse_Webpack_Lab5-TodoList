<template>
    <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <!-- slot會承接從外部傳進來的內容 -->
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            quotes: {
                type: Array
            }
        }
    }
</script>

<style>
    .panel-body {
        font-family: 'Arizonia', cursive;
        font-size: 24px;
        color: #6e6e6e;
    }

    .quote {
        cursor: pointer;
    }

    .quote:hover {
        background-color: #ffe2e2;
    }
</style>
