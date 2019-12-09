<template>
    <div id="convert-to-jap">
        <h2> <span class="converted-title">Romaji：</span> <span class="converted">{{showRomaji ? showRomaji : '---'}}</span></h2>
        <h2> <span class="converted-title">Kana：</span> <span class="converted">{{showKana ? showKana :  '---'}}</span></h2>
        <h2> <span class="converted-title">Hiragana：</span> <span class="converted">{{showHiragana ? showHiragana :  '---'}}</span></h2>
        <h2> <span class="converted-title">Katakana：</span> <span class="converted">{{showKatakana ? showKatakana :  '---'}}</span></h2>
        <h2><span class="converted-title">入力してください：</span><input type="text" v-model="origin" class="origin-input"></h2>
    </div>
</template>

<script>
    import * as wanakana from 'wanakana';
    //import wanakana from 'wanakana';


    export default {
        name: "ConvertToJap",
        data() {
            return {
                origin: '',
                romaji:''

            }
        },
        methods:{

        },
        computed: {
            showRomaji() {
                return wanakana.toRomaji(this.origin)
            },
            showKana() {
                return wanakana.toKana(this.origin)
            },
            showHiragana() {
                return wanakana.toHiragana(this.origin)
            },
            showKatakana() {
                return wanakana.toKatakana(this.origin)
            }
        }
    }
</script>



<style scoped>
    #convert-to-jap .converted{
        color:#3eaf7c;
        width: 200px;
        display: inline-block;
        text-align: left;
    }
    .converted-title {
        width: 260px;
        display: inline-block;
        text-align: right;
    }
    .origin-input {
        height: 40px;
        width: 200px;
        border: 1px solid #3eaf7c;
        font-size: 30px;
    }
    .origin-input:focus {
        border-style:solid;
        box-shadow: 0 0 6px #3eaf7c;
    }
</style>
