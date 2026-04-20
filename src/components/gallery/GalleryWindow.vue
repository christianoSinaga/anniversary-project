<template>
  <div class="flex flex-col gap-5 items-center w-full overflow-hidden">
    <h1 class="flex gap-2 text-2xl items-center font-bold text-pink-700">
      <Camera :size="24" />
      Love Gallery
    </h1>

    <div class="w-full overflow-x-auto">
      <div class="flex gap-4 p-6">
        <div
          v-for="item in galleries"
          :key="item.id"
          class="min-w-62.5 bg-white rounded-2xl shadow-lg overflow-hidden"
        >
          <img
            :src="item.url"
            loading="lazy"
            class="w-full h-60 object-cover hover:scale-110 transition duration-500"
          />
        </div>
      </div>
    </div>

    <p class="text-sm flex-wrap p-6 text-center text-gray-600">
      Foto-foto ini adalah momen-momen yang sudah kita lewati bersama, mulai dari yang pertama kali
      kita bertemu, jalan-jalan, sampai yang terakhir kita habiskan bersama. Maap kalo fotonya
      enggak bannyak soalnya proses pengembangan web ini cukup mepet hehe
    </p>
  </div>
</template>

<script setup>
import Camera from '@/assets/icons/Camera.vue'

const galleries = [
  {
    id: 1,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244052/IMG_20251211_205747_l03spf.jpg',
  },
  {
    id: 2,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244052/IMG_20251226_164243_wq1k0v.jpg',
  },
  {
    id: 3,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244051/IMG_20251211_205804_snuzed.jpg',
  },
  {
    id: 4,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244051/IMG_20250419_213252_ruajuh.jpg',
  },
  {
    id: 5,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244051/IMG_20251230_140158_nu0qko.jpg',
  },
  {
    id: 6,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244051/IMG_20250907_173005_2_lbzc5c.jpg',
  },
  {
    id: 7,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244049/IMG_20250406_185615_ylon5x.jpg',
  },
  {
    id: 8,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244049/IMG_20250907_172307_rbcbn7.jpg',
  },
  {
    id: 9,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244049/IMG_20250419_213251_hncxc6.jpg',
  },
  {
    id: 10,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244048/IMG_20250406_185618_vhoq7u.jpg',
  },
  {
    id: 11,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244048/IMG_20251212_190005_ke1gm7.jpg',
  },
  {
    id: 12,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244047/IMG_20250406_185707_bnrciz.jpg',
  },
  {
    id: 13,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244046/IMG_20250628_181754_v0emuo.jpg',
  },
  {
    id: 14,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244046/IMG_20251212_190017_ms88wy.jpg',
  },
  {
    id: 15,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244046/IMG_20251230_164729_xvwali.jpg',
  },
  {
    id: 16,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244044/IMG_20251212_192342_ijwotc.jpg',
  },
  {
    id: 17,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244041/IMG_20250628_181755_sb88n9.jpg',
  },
  {
    id: 18,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244039/IMG_20250423_131838_ffklsy.jpg',
  },
  {
    id: 19,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244035/IMG_20250406_190143_twxuua.jpg',
  },
  {
    id: 20,
    url: 'https://res.cloudinary.com/dj9jj0bsd/image/upload/q_auto/f_auto/v1776244021/IMG_20251212_192256_v65i3m.jpg',
  },
]
</script>

<style scoped>
h1 {
  font-family: 'Cardo', serif;
}
</style>
