<script setup lang="ts">
import { VPTeamMembers } from 'vitepress/theme'
import { siteName } from '../../../metadata'
import {ref} from 'vue';

const data = ref([
{
    category: "🔗 常用工具",
    items: [
        {title: "海棠诗社",desc: "古诗词的数字桃源",link: "https://haitang.app"},
        {title: "海棠诗社",desc: "古诗词的数字桃源",link: "https://haitang.app"},
        {title: "海棠诗社",desc: "古诗词的数字桃源",link: "https://haitang.app"},
        {title: "海棠诗社",desc: "古诗词的数字桃源",link: "https://haitang.app"},
        {title: "海棠诗社",desc: "古诗词的数字桃源",link: "https://haitang.app"},
        {title: "海棠诗社",desc: "古诗词的数字桃源",link: "https://haitang.app"},
        {title: "海棠诗社",desc: "古诗词的数字桃源",link: "https://haitang.app"},
    ]
},
])

</script>

<template>
<div class="grid-container">
    <div class="row" v-for="v,k in data" :key="k">
        <div class="nav_title">{{ v.category }}</div>
        <div class="nav_cards">
            <!-- 导航卡片 -->
            <a class="card" v-for="v2,k2 in v.items" :key="k2" :href="v2.link" target="_blank">
                <div class="card_title">{{ v2.title }}</div>
                <p class="card_desc">{{ v2.desc }}</p>
            </a>
        </div>
    </div>
    
</div>

</template>


<style scoped>
/*网格容器样式*/
.grid-container {
    padding: 0 20px;
    width: 100%;
    height: 100%;
}

.row {
    width: 100%;
    height: 100%;
}


.nav_cards {
    display: grid;
    grid-template-columns: repeat(6, 1fr); /*每行6张卡片*/
    gap: 20px; /*行间距*/
    
}

/*卡片样式*/
.card {
    background-color: #f0f0f0;
    padding: 6px 10px;
    border-radius: 4px;
    box-sizing: border-box;
    /* width: 190px; */
}
.card:hover {
    transform: translateY(-5px);
    box-shadow: 0px 0px 20px -5px rgba(158, 158, 158, .2);
    border-radius: 0;
    transition: all 0.3s ease;
    cursor: pointer;
}
.card_title {
    font-size: 14px;
    font-weight: blod;
}
.card_desc {
    color: #6c757d;
    font-size: 12px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}

.nav_title {

    display: flex;
    align-items: center;
    height: 60px;

    font-size: 18px;
    color: #555;
    
}

/*响应式设计*/
@media (max-width: 768px) {
    .nav_cards {
        grid-template-columns: repeat(3, 1fr); /*调整为三列*/
    }
}
</style>