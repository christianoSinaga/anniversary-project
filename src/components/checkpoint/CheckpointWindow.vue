<template>
  <!-- Checkpoint Cards Container -->
  <!-- Tampil 3 kiri 3 kanan -->
  <div class="flex flex-col flex-wrap gap-5 items-center justify-center">
    <h1 class="flex items-center gap-2 text-2xl font-bold text-pink-700">
      <CalenderCheck />
      Love Timeline
    </h1>
    <div class="flex flex-col gap-2 text-center">
      <p class="text-sm text-gray-800">
        Banyak banget hal-hal yang udah kita lewatin bareng bareng.
      </p>
      <p class="text-sm text-gray-800">Aku nandain {{ checkpoints.length }} momen spesial kita.</p>
    </div>
    <CheckpointCards
      v-for="checkpoint in checkpoints"
      :key="checkpoint.id"
      :checkpoint="checkpoint"
    />
  </div>
</template>

<script setup>
import CalenderCheck from '@/assets/icons/CalenderCheck.vue'
import CheckpointCards from './CheckpointCards.vue'

const checkpoints = [
  {
    id: 1,
    title: 'First Meet',
    desc: 'Momen pertama aku ketemu kamu, aku masih inget banget waktu latihan koor bareng buat pesta resort di HKBP Perak. Mungkin kamu enggak notice aku waktu itu, tapi aku masih inget banget semua kejadiannya dari awal sampe akhir. Saat istirahat, aku diberi tahu bg Gideon tentang kamu dan rasa penasaranku langsung muncul. Mulai saat itulah aku mulai ngeperhatiin kamu dari jauh',
    date: '9 Maret 2025',
  },
  {
    id: 2,
    title: 'DM IG Pertama',
    desc: 'Momen pertama kita komunikasi lewat DM IG, di mana sebenernya aku ngefollow kamu duluan juga karna dipencetin sama temen, tapi aku gak pernah nyangka kamu bakal bales DM aku. Aku masih inget banget waktu itu kamu bales DM aku dengan kata-kata yang sederhana tapi bikin aku seneng banget. Yang bahkan saat itu aku masih manggil kamu pake sebutan "kak" karena aku masih merasa kamu itu sosok yang jauh dari aku',
    date: '15 Maret 2025',
  },
  {
    id: 3,
    title: 'Fotbar Pertama',
    desc: 'Momen saat aku masih malu malu buat nyamperin kamu, sampe di titik temen aku Christison (Encis) yang akhirnya nyampaiin ke kamu kalo aku pengen foto sama kamu. Karna saat itu timingnya udah bener bener pas tapi aku masih belum beranih buat nyamperin kamu. Aku juga inget kalo waktu itu yang ngefotoin kita adalah orang yang ternyata enggak kamu suka yaitu Gilbert wkwkwk',
    date: '16 Maret 2025',
  },
  {
    id: 4,
    title: 'First Date (Unofficial)',
    desc: 'Memang sebenernya agak tragis, tapi aku masih inget banget date pertama kita yang aku juga enggak tau kamu mau nganggep itu sebagai date atau enggak. Date pertama kita itu sebenernya terjadi waktu kamu di opname karna sakit tipes. Aku inget banget waktu itu aku dateng bareng sama temen temen aku yang lain, sambil aku bawa buah buahan buat jajan kamu. Momennya meskipun kamu lagi sakit tapi di situ aku ngerasa kita udah kayak lagi ngedate aja, kita ngobrol banyak banget karena itu pertama kali kita ketemu setelah kita mulai dekat',
    date: '26 Maret 2025',
  },
  {
    id: 5,
    title: 'First Date (Official)',
    desc: 'Mungkin momen ini yang mau kamu anggep sebagai first date kita. Yaitu saat kamu dateng ke gereja aku di saat aku bertugas sebagai pianis ibadah. Saat kamu muncul dari pintu depan itu aku langsung sadar kalo itu kamu, meskipun dari jauh aku langsung bisa ngenalin kamu. Aku inget banget waktu itu aku langsung seneng banget karena kamu dateng buat dengerin aku main piano, dan itu bener bener bikin aku ngerasa spesial banget. Kita ngobrol banyak banget setelah ibadah selesai, dan itu bener bener jadi momen yang gak akan pernah aku lupain',
    date: '30 Maret 2025',
  },
  {
    id: 6,
    title: 'Conffession',
    desc: 'Meskipun agak lucu sebenernya kalo diinget-inget, tapi momen saat aku nembak kamu itu juga jadi salah satu momen yang gak akan pernah aku lupain. Aku make gimmick "baju serius" aku buat nembak kamu dan biar enggak dianggap bercanda sama kamu. Sedih dikit juga memang kalo inget ternyata aku nembak kamu itu ternyata kejadiannya lewat video call, karena waktu itu kita enggak bisa ketemu dan aku dikejar dengan kondisi kamu yang bener bener ngebet mau ditembak saat itu juga + Kevin yang sudah keliatan bakal nembak kamu juga hari itu.',
    date: '21 April 2025',
  },
  {
    id: 7,
    title: 'LDR',
    desc: 'Masih berjalan sampe sekarang, sebuah kondisi yang kita sama sama enggak suka tapi kita harus jalanin bareng bareng. Meskipun kita sama sama gak suka, tapi aku tetep bersyukur banget karena kita bisa jalanin LDR ini bareng bareng, dan aku yakin kita bisa lewatin semua rintangan yang ada di depan kita. Aku juga yakin kalo suatu saat nanti kita bakal bisa ketemu lagi tanpa harus lewatin LDR lagi, dan itu bakal jadi momen yang paling spesial banget buat kita berdua',
    date: '29 Juni 2025 - Sekarang',
  },
]
</script>

<style scoped>
h1 {
  font-family: 'Cardo', serif;
}
</style>
