<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import Card from '@/Components/Card.vue';
import { Head } from '@inertiajs/vue3';


const comp_accessories = [
    {
        id: 1,
        name: 'Tama Drums',
        thumbnail: 'https://images-na.ssl-images-amazon.com/images/I/811Rl6bMadL._AC_SL1500_.jpg',
        price: '42,999.00 Php'
    },

];
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-900 leading-tight">Dashboard</h2>
        </template>

        <div class="max-w-5xl sm:px-6 lg:px-8 flex mx-auto mt-8 mb-8">
            <table class="w-full bg-gray-200 border-collapse sm:rounded-lg">
              <thead>
                <tr class="bg-gray-400 text-black">
                  <th class="p-3">Drum Name</th>
                  <th class="p-3">Photo</th>
                  <th class="p-3">Price</th>
                  <th class="p-3">Actions</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="comp_accessory in comp_accessories" :key="comp_accessory.id" class="">
                  <td>
                    <Card>
                      <template v-slot:header>
                        <h1 class="2xl flex justify-center">{{ comp_accessory.name }}</h1>
                      </template>
                    </Card>
                  </td>
                  <td>
                    <Card>
                      <template v-slot:default>
                        <div class="flex justify-center">
                          <img :src="comp_accessory.thumbnail" alt="" style="width: 80px; height: 80px;" class="rounded-full">
                        </div>
                      </template>
                    </Card>
                  </td>
                  <td>
                    <Card>
                      <template v-slot:content1>
                        <h1 class="2xl flex justify-center text-gray-900">{{ comp_accessory.price }}</h1>
                      </template>
                    </Card>
                  </td>
                  <td>
                    <Card>
                      <template v-slot:footer>
                        <div class="flex justify-center">
                          <button class="bg-gray-600 text-white p-2 rounded shadow-md hover:bg-gray-100 hover:text-black">
                            Buy Now
                          </button>
                        </div>
                      </template>
                    </Card>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>



            <div v-for="comp_accessory in comp_accessories" :key="comp_accessory.id" class="bg-gray-200 justify-center rounded-lg shadow-lg max-w-9xl">
                <div class="columns-6 gap-y-6 mt-6">
                    <Card class="py-12 ">
                        <template v-slot:default>
                            <div class>
                                <img :src="comp_accessory.thumbnail" alt="" class="w-full aspect-circle rounded ">
                            </div>
                        </template>
                        <template v-slot:content1>
                            <div class="mt-4">
                                <h1 class="2xl flex justify-center text-gray-900">For sale {{ comp_accessory.name }}, Buy now {{ comp_accessory.price }}. retail price</h1>
                            </div>
                        </template>
                        <template v-slot:footer>
                            <button class="bg-gray-700 text-white flex justify-center p-2 rounded shadow-md shadow-gray-500/50 hover:bg-gray-100  hover:text-black mt-12">
                            Buy Now
                            </button>
                        </template>
                    </Card>
                </div>

            </div>







          <div class="bg-white flex flex-col gap-8 items-center justify-center">
            <div class="max-w-5xl sm:px-9 lg:px-9">
                <div class="bg-gray-200 flex justify-center overflow-hidden shadow-sm sm:rounded-lg mt-8">
                    <div class="grid3 mx-auto">
                        <div v-for="comp_accessory in comp_accessories" :key="comp_accessory.id" class="m-3 bg-gray-900 text-gray-100 rounded-lg">
                            <Card>
                                    <template v-slot:header>
                                        <h1 class="2xl flex justify-center">{{ comp_accessory.name }}</h1>
                                    </template>
                                    <template v-slot:default>
                                        <div>
                                            <img :src="comp_accessory.thumbnail" alt="" style="width: 320px; height:220px;">
                                        </div>
                                    </template>
                                    <template v-slot:content1>
                                        <h1 class=" bg-gray-200 2xl flex justify-center text-gray-900">{{ comp_accessory.price }}</h1>
                                    </template>
                                    <template v-slot:footer >
                                        <!-- <h1 class="2xl flex justify-center">{{ comp_accessory.name }}</h1> -->
                                        <div class="flex justify-center">
                                            <button class="bg-gray-500 flex justify-center p-2 rounded shadow-md shadow-gray-500/50 hover:bg-gray-100 hover:text-black mt-12">
                                                Buy Now
                                                </button>
                                        </div>

                                    </template>
                            </Card>
                        </div>
                    </div>
                </div>
            </div>

    </div>



    </AuthenticatedLayout>
</template>

<style scoped>
.grid1{
    display: grid;
    grid-template-columns: repeat(3,1fr);
    gap: 24px 24px;
}


</style>
