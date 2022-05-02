<template>
  <div class="">
  <div class="mx-auto max-w-screen-xl">
    <div style="grid-template-columns: 1fr 2fr 3fr;" class="grid gap-4 m-4">
      <img
          src="https://dl.airtable.com/.attachments/d9bbf6ad20c489a45798a5521f172900/3c5f3955/FS-vi3x.jpg?ts=1651380770&userId=usrk5orn56sTujaim&cs=93ddea87543d8c20"
      />
      <div
          class="text-2xl"
      >
        Chào mừng bạn đến với trung tâm yêu thích trái cây, thêm vào giỏ hàng yêu thích của bạn ngay bây giờ và tận
        hưởng ưu đãi có thời hạn này nhé:
      </div>
      <Search/>
    </div>
    <div style="grid-template-columns: 3fr 1fr;" class="grid gap-4 m-4">
      <div>
        <img
            src="https://suno.vn/blog/wp-content/uploads/2018/04/ban-trai-cay-1-e1522999658283.jpg"
            style="object-fit: cover; width: 100%; max-height: 200px;"
        />
        <br>
        <Taps/>
      </div>
      <div>
        <div
            class="font-bold text-2xl mb-3"
        >
          Giỏ hàng
        </div>
        <Cart/>
        <div
            class="mt-3" style="text-emphasis-color: red"
        >
          Chúng tôi có những sản phẩm tươi nhất !
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script lang="ts">
import {Component} from "Vue";
import Taps from 'growlers/Taps';
import Search from 'growlers/Search';
import Cart from 'growlers/Cart';
import store from 'growlers/store';

export default {
  components: {
    Search,
    Taps,
    Cart,
  },
  computed: {
    filteredTaps: {
      get() {
        return store.filteredTaps.slice(0, 3).map(({beverageName}: { beverageName: string }) => beverageName).join(', ');
      },
      set() {
      }
    }
  }
}
</script>