<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts" >
    import { ref } from 'vue'

    const sectionOpen = ref(1)

</script>


<template>

    <div class="flex flex-col gap-5">
        <section>
            <button class="text-xl bg-cyan-500 hover:bg-cyan-600 rounded-xl px-2 " @pointerdown="sectionOpen = 1/* change `sectionOpen` à 1 */">bouton 1</button>
            <p v-show="sectionOpen == 1/* teste si `sectionOpen` est égale à 1 */">Lorem ipsum dolor sit amet consectetur adipisicing elit. Qui dolorem aperiam nisi! Atque, reiciendis dolorem earum eos, exercitationem quidem nobis quo suscipit optio sapiente vel nihil doloremque recusandae dignissimos! Assumenda.</p>
        </section>
        <section>
            <button class="text-xl bg-cyan-500 hover:bg-cyan-600 rounded-xl px-2 " @pointerdown="sectionOpen = 2/* change `sectionOpen` à 2 */">bouton 2</button>
            <p v-show="sectionOpen == 2/* teste si `sectionOpen` est égale à 2 */">Obcaecati placeat vel dolore? Atque iusto asperiores adipisci, odit vitae iste, magni ipsa provident fugiat eius numquam error laborum consequatur accusamus placeat. Aliquam, cumque. Corporis magni repudiandae obcaecati vero laudantium.</p>
        </section>
        <section>
            <button class="text-xl bg-cyan-500 hover:bg-cyan-600 rounded-xl px-2" @pointerdown="sectionOpen = 3/* change `sectionOpen` à 3 */">bouton 3</button>
            <p v-show="sectionOpen == 3/* teste si `sectionOpen` est égale à 3 */">Tempore quis, numquam at ipsum distinctio reprehenderit consectetur inventore unde perferendis dolorem dignissimos ut veniam voluptatibus officiis eveniet sapiente cupiditate nesciunt pariatur quasi quia? Vitae maxime sint hic voluptatem et.</p>
        </section>
    </div>

</template>