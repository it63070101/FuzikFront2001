<template>
    <div class="h-screen bg-slate-800">
        <div class="fixed flex items-center justify-center top-0 left-0 right-0 bottom-0 z-80" id='popup' v-if="loginStatus">
            <div class="flex flex-col bg-white rounded-xl w-1/4 h-1/5 p-6 gap-6 text-center">
                <p>You didn't Login.Please Login First</p>
                <a href="http://fuzik.co/dashboard" class="bg-yellow-400 p-3 rounded-xl text-center">Accept</a>
            </div>
        </div>
        <!-- navbar popup-->
        <div class="Navmenu fixed flex z-70 w-full h-full" v-if="openMenu">
            <div class="flex flex-col md:w-1/5 h-full bg-slate-800 p-6">
                <div class="flex items-center flex-row gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="color h-8" @click="openNav">
                    <path d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg>
                    <img src="http://fuzik.co/wp-content/uploads/2023/03/5f8ffb_0b6776edbdab41019a1c8f35aeae13c6_mv2.png" class="w-40">
                </div>
                <div class="p-1">
                    <div class="grid gap-y-2">
                        <div class="grid grid-cols-3 p-2 items-center rounded-xl hover:bg-slate-900">
                            <div class="grid col-span-1 place-items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 icon" viewBox="0 0 576 512">
                                <path d="M575.8 255.5c0 18-15 32.1-32 32.1h-32l.7 160.2c0 2.7-.2 5.4-.5 8.1V472c0 22.1-17.9 40-40 40H456c-1.1 0-2.2 0-3.3-.1c-1.4 .1-2.8 .1-4.2 .1H416 392c-22.1 0-40-17.9-40-40V448 384c0-17.7-14.3-32-32-32H256c-17.7 0-32 14.3-32 32v64 24c0 22.1-17.9 40-40 40H160 128.1c-1.5 0-3-.1-4.5-.2c-1.2 .1-2.4 .2-3.6 .2H104c-22.1 0-40-17.9-40-40V360c0-.9 0-1.9 .1-2.8V287.6H32c-18 0-32-14-32-32.1c0-9 3-17 10-24L266.4 8c7-7 15-8 22-8s15 2 21 7L564.8 231.5c8 7 12 15 11 24z"/></svg>
                            </div>
                            <div class="col-span-2 text-lg text-yellow-300">Home</div>
                        </div>
                        <div class="grid grid-cols-3 p-2 items-center rounded-xl hover:bg-slate-900">
                            <div class="grid col-span-1 place-items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="h-8 icon">
                                <path d="M246.6 9.4c-12.5-12.5-32.8-12.5-45.3 0l-128 128c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L192 109.3V320c0 17.7 14.3 32 32 32s32-14.3 32-32V109.3l73.4 73.4c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3l-128-128zM64 352c0-17.7-14.3-32-32-32s-32 14.3-32 32v64c0 53 43 96 96 96H352c53 0 96-43 96-96V352c0-17.7-14.3-32-32-32s-32 14.3-32 32v64c0 17.7-14.3 32-32 32H96c-17.7 0-32-14.3-32-32V352z"/></svg>
                            </div>
                            <div class="col-span-2 text-lg text-yellow-300">Uploads</div>
                        </div>
                        <div class="grid grid-cols-3 p-2 items-center rounded-xl hover:bg-slate-900">
                            <div class="grid col-span-1 place-items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 icon" viewBox="0 0 640 512">
                                <path d="M96 128a128 128 0 1 1 256 0A128 128 0 1 1 96 128zM0 482.3C0 383.8 79.8 304 178.3 304h91.4C368.2 304 448 383.8 448 482.3c0 16.4-13.3 29.7-29.7 29.7H29.7C13.3 512 0 498.7 0 482.3zM609.3 512H471.4c5.4-9.4 8.6-20.3 8.6-32v-8c0-60.7-27.1-115.2-69.8-151.8c2.4-.1 4.7-.2 7.1-.2h61.4C567.8 320 640 392.2 640 481.3c0 17-13.8 30.7-30.7 30.7zM432 256c-31 0-59-12.6-79.3-32.9C372.4 196.5 384 163.6 384 128c0-26.8-6.6-52.1-18.3-74.3C384.3 40.1 407.2 32 432 32c61.9 0 112 50.1 112 112s-50.1 112-112 112z"/></svg>
                            </div>
                            <div class="col-span-2 text-lg text-yellow-300">Collaboration</div>
                        </div>
                        <div class="grid grid-cols-3 p-2 items-center rounded-xl hover:bg-slate-900">
                            <div class="grid col-span-1 place-items-center">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 icon" viewBox="0 0 576 512">
                                <path d="M0 128C0 92.7 28.7 64 64 64H320c35.3 0 64 28.7 64 64V384c0 35.3-28.7 64-64 64H64c-35.3 0-64-28.7-64-64V128zM559.1 99.8c10.4 5.6 16.9 16.4 16.9 28.2V384c0 11.8-6.5 22.6-16.9 28.2s-23 5-32.9-1.6l-96-64L416 337.1V320 192 174.9l14.2-9.5 96-64c9.8-6.5 22.4-7.2 32.9-1.6z"/></svg>
                            </div>
                            <div class="col-span-2 text-lg text-yellow-300">Your Video</div>
                        </div>
                    </div>
                </div>
            </div> 
        </div>
        <!-- Navbar -->
        <div class="flex items-center p-2 mx-3 gap-2">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" class="color h-8 md:h-12" @click="openNav">
            <path d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg>
            <img src="http://fuzik.co/wp-content/uploads/2023/03/5f8ffb_0b6776edbdab41019a1c8f35aeae13c6_mv2.png" class="w-40 md:w-56">
            <div class="grow"></div>
            <button class="p-3 bg-yellow-300 rounded-lg text-sm md:text-lg">Register/Login</button>
            <!-- <a href="https://fuzik.co/dashboard" class="p-3 bg-yellow-300 rounded-lg text-sm md:text-lg">register/login</a> -->
        </div>
        <!-- Popup -->
        <div v-if="toggleModal" class="fixed flex items-center justify-center top-0 left-0 right-0 bottom-0 z-50" id="popup">
            <div class="relative mx-auto p-5 bg-slate-800 max-w-2xl w-auto rounded-xl">
                <div class="py-2 flex justify-center">
                    <input type="text" class="p-2 w-96" v-model="searchValue" placeholder="Typing Your Songs"> 
                </div>
                
                <div class="relative mx-auto max-w-2xl w-auto bg-slate-700 h-80 p-3 overflow-auto" v-if="vdo == 'landscape'">
                    <div v-for="(item, index) in itemList"
                        class="grid grid-cols-2 cursor-pointer bg-slate-600 w-full h-auto mt-3 p-3 rounded-lg hover:bg-yellow-400"
                        @click="SelectVDO(index)"
                    >
                        <img :src="item.preview" class="w-3/4">
                        {{ item.music_title }}
                    </div>
                </div>

                <div class="relative mx-auto max-w-2xl w-auto bg-slate-700 h-80 p-3 overflow-auto" v-if="vdo == 'portait'">
                    <div v-for="(item, index) in itemListP"
                        class="grid grid-cols-2 cursor-pointer bg-slate-600 w-auto h-auto mt-3 p-3 rounded-lg hover:bg-yellow-400"
                        @click="SelectVDO(index)"
                    >
                        <img :src="item.preview" class="w-1/2">
                        {{ item.music_title }}
                    </div> 
                </div>

                <div class="flex flex-row-reverse mx-auto max-w-2xl gap-2">
                    <button @click="addVideo" class="p-3 rounded-lg bg-yellow-300 mt-3">Add Video</button>
                    <button @click="closeBtn" class="p-3 rounded-lg bg-red-500 mt-3">Close</button>    
                </div> 
            </div>
        </div>
        <!-- VDO Sample -->
        <div class="flex justify-center items-center h-3/5 lg:h-3/5">
            <div class="flex justify-center items-center bg-slate-700 rounded-xl h-5/6 w-96 md:w-3/5">
                <div v-if="layoutSelect">
                    <!-- Layout 0 -->
                    <div class="flex justify-center" v-if="isLayout === 0">
                        <div class="flex flex-nowrap items-center w-auto h-auto p-2">
                            <div class="flex justify-center items-center bg-slate-800 w-40 h-64 md:w-48 md:h-80 rounded-xl" v-if="JSON.stringify(selected[0]) === '{}'">
                                <button @click="togglePopup('portait',0)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                            </div>
                                <div class="flex items-center w-32 h-40 md:w-48 md:h-80" v-else>
                                    <img :src="selected[0].preview">
                                </div>
                            <div class="flex justify-center items-center bg-slate-800 ml-1 w-44 h-32 md:w-64 md:h-40 rounded-xl" v-if="JSON.stringify(selected[1]) === '{}'">
                                <button @click="togglePopup('landscape',1)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                            </div>
                                <div class="flex items-center ml-1 w-44 h-28 md:w-64 md:h-40 rounded-xl" v-else>
                                    <img :src="selected[1].preview">
                                </div>
                        </div>
                    </div>
                    <!-- Layout 1 -->
                    <div class="flex justify-center" v-else-if="isLayout === 1">
                        <div class="flex flex-nowrap items-center w-auto h-auto p-2">
                            <div class="flex items-center justify-center bg-slate-800 ml-1 w-44 h-32 md:w-64 md:h-40 rounded-xl"  v-if="JSON.stringify(selected[0]) === '{}'">
                                <button @click="togglePopup('landscape',0)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                            </div>
                                <div class="flex items-center w-44 h-28 md:w-64 md:h-40 rounded-xl" v-else>
                                    <img :src="selected[0].preview">
                                </div>
                            <div class="flex justify-center items-center bg-slate-800 ml-1 w-44 h-32 md:w-64 md:h-40 rounded-xl"  v-if="JSON.stringify(selected[1]) === '{}'">
                                <button @click="togglePopup('landscape',1)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                            </div>
                                <div class="flex items-center ml-1 w-44 h-28 md:w-64 md:h-40 rounded-xl" v-else>
                                    <img :src="selected[1].preview">
                                </div>
                        </div>
                    </div>
                    <!-- Layout 2 -->
                    <div class="flex justify-center" v-else-if="isLayout === 2">
                        <div class="flex flex-col items-center w-auto h-auto p-2">
                            <div class="flex justify-center items-center bg-slate-800 mb-1 rounded-xl w-64 h-40"  v-if="JSON.stringify(selected[0]) === '{}'">
                                <button @click="togglePopup('landscape',0)" class="px-5 py-3 bg-yellow-300 rounded-lg">Select</button>
                            </div>
                                <div class="flex items-center w-64 h-40 rounded-xl" v-else>
                                    <img :src="selected[0].preview">
                                </div>
                            <div class="flex justify-center items-center bg-slate-800 w-64 h-40 rounded-xl"  v-if="JSON.stringify(selected[1]) === '{}'">
                                <button @click="togglePopup('landscape',1)" class="px-5 py-3 bg-yellow-300 rounded-lg">Select</button>
                            </div>
                                <div class="flex items-center ml-1 w-64 h-40 rounded-xl" v-else>
                                    <img :src="selected[1].preview">
                                </div>
                        </div>
                    </div>
                    <!-- Layout 3 -->
                    <div class="flex justify-center" v-else-if="isLayout === 3">
                        <div class="flex flex-nowrap justify-center items-center w-auto h-auto">
                            <div class="flex items-center justify-center bg-slate-800 rounded-xl w-40 h-64 md:w-48 md:h-80" v-if="JSON.stringify(selected[0]) === '{}'">
                                <button @click="togglePopup('portait',0)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button> 
                            </div>
                                <div class="flex items-center w-40 h-48 md:w-48 md:h-80 rounded-xl" v-else>
                                    <img :src="selected[0].preview">
                                </div>
                            <div class="flex justify-center items-center bg-slate-800 rounded-xl ml-1 w-40 h-64 md:w-48 md:h-80"  v-if="JSON.stringify(selected[1]) === '{}'">
                                <button @click="togglePopup('portait',1)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>  
                            </div>
                                <div class="flex items-center w-40 h-48 md:w-48 md:h-80 ml-1 rounded-xl" v-else>
                                    <img :src="selected[1].preview">
                                </div>
                        </div>
                    </div>
                    <!-- Layout 4 -->
                    <div class="flex justify-center" v-else-if="isLayout === 4">
                        <div class="flex gap-2">
                            <div class="flex justify-center items-center bg-slate-800 rounded-xl h-88 w-36 md:w-48 md:h-80" v-if="JSON.stringify(selected[0]) === '{}'">
                                <button @click="togglePopup('portait',0)" class="px-5 py-3 bg-yellow-300 rounded-lg">Select</button>    
                            </div>
                            <div class="flex items-center w-32 h-48 md:w-48 md:h-80" v-else>
                                <img :src="selected[0].preview">
                            </div>
                            <div class="flex flex-col gap-y-2 lg:gap-y-1">
                                <div class="flex justify-center items-center bg-slate-800 rounded-xl h-44 w-52 md:w-64 md:h-40" v-if="JSON.stringify(selected[1]) === '{}'">
                                    <button @click="togglePopup('landscape',1)" class="px-5 py-3 bg-yellow-300 rounded-lg">Select</button>    
                                </div>
                                <div class="flex items-center w-44 h-24 md:w-64 md:h-40" v-else>
                                    <img :src="selected[1].preview">
                                </div>
                                <div class="flex justify-center items-center bg-slate-800 rounded-xl h-44 w-52 md:w-64 md:h-40" v-if="JSON.stringify(selected[2]) === '{}'">
                                    <button @click="togglePopup('landscape',2)" class="px-5 py-3 bg-yellow-300 rounded-lg">Select</button>  
                                </div>
                                <div class="flex items-center w-44 h-24 md:w-64 md:h-40" v-else>
                                    <img :src="selected[2].preview">
                                </div>
                            </div>
                        </div>
                    </div>
                    <!-- Layout 5 -->
                    <div class="flex justify-center" v-else-if="isLayout === 5">
                        <div class="flex flex-col items-center gap-y-2">
                            <div class="flex flex-row gap-2">
                                <div class="flex justify-center items-center bg-slate-800 rounded-xl w-44 h-28 md:w-64 md:h-40" v-if="JSON.stringify(selected[0]) === '{}'">
                                    <button @click="togglePopup('landscape',0)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                                </div>
                                <div class="flex md:items-center w-44 h-36 md:w-64 md:h-40" v-else>
                                    <img :src="selected[0].preview">
                                </div>
                                <div class="flex justify-center items-center bg-slate-800 rounded-xl w-44 h-28 md:w-64 md:h-40" v-if="JSON.stringify(selected[1]) === '{}'">
                                    <button @click="togglePopup('landscape',1)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                                </div>
                                <div class="flex md:items-center w-44 h-36 md:w-64 md:h-40" v-else>
                                    <img :src="selected[1].preview">
                                </div>
                            </div>
                            <div class="flex justify-center items-center bg-slate-800 rounded-xl w-48 h-28 md:w-64 md:h-40" v-if="JSON.stringify(selected[2]) === '{}'">
                                <button @click="togglePopup('landscape',2)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                            </div>
                            <div class="flex md:justify-center md:items-center w-3/5 h-36 md:w-64 md:h-40" v-else>
                                <img :src="selected[2].preview">
                            </div>
                        </div>
                    </div>
                    <!-- Layout 6 -->
                    <div class="flex justify-center" v-else-if="isLayout === 6">
                        <div class="flex flex-row justify-center items-center w-auto h-auto gap-2">
                            <div class="flex justify-center items-center bg-slate-800 w-28 h-56 md:w-48 md:h-80 rounded-xl" v-if="JSON.stringify(selected[0]) === '{}'">
                                <button @click="togglePopup('portait',0)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                            </div>
                                <div class="flex items-center w-28 h-40 md:w-48 md:h-80" v-else>
                                    <img :src="selected[0].preview">
                                </div>
                                <div class="flex justify-center items-center bg-slate-800 w-28 h-56 md:w-48 md:h-80 rounded-xl" v-if="JSON.stringify(selected[1]) === '{}'">
                                <button @click="togglePopup('portait',1)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                            </div>
                                <div class="flex items-center w-28 h-40 md:w-48 md:h-80" v-else>
                                    <img :src="selected[1].preview">
                                </div>
                                <div class="flex justify-center items-center bg-slate-800 w-28 h-56 md:w-48 md:h-80 rounded-xl" v-if="JSON.stringify(selected[2]) === '{}'">
                                <button @click="togglePopup('portait',2)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                            </div>
                                <div class="flex items-center w-28 h-40 md:w-48 md:h-80" v-else>
                                    <img :src="selected[2].preview">
                                </div>
                        </div>
                    </div>
                    <!-- Layout 7 -->
                    <div class="flex justify-center" v-else-if="isLayout === 7">
                        <div class="grid grid-cols-2 grid-rows-2 w-auto h-auto p-1 gap-2 md:gap-4">
                            <div class="grid col-span-1 row-span-1 bg-slate-800 w-36 h-40 md:w-64 md:h-40 rounded-xl" v-if="JSON.stringify(selected[0]) === '{}'">
                                <div class="flex justify-center self-center">
                                    <button @click="togglePopup('landscape',0)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                                </div>
                            </div>
                                <div class="flex items-center md:w-64 md:h-40" v-else>
                                    <img :src="selected[0].preview">
                                </div>
                            <div class="grid col-span-1 row-span-1 bg-slate-800 w-36 h-40 md:w-64 md:h-40 rounded-xl" v-if="JSON.stringify(selected[1]) === '{}'">
                                <div class="flex self-center justify-center">
                                    <button @click="togglePopup('landscape',1)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                                </div>
                            </div>
                                <div class="flex items-center md:w-64 md:h-40" v-else>
                                    <img :src="selected[1].preview">
                                </div>
                            <div class="grid col-span-1 row-span-1 bg-slate-800 w-36 h-40 md:w-64 md:h-40 rounded-xl" v-if="JSON.stringify(selected[2]) === '{}'">
                                <div class="flex justify-center self-center">
                                    <button @click="togglePopup('landscape',2)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                                </div>
                            </div>
                                <div class="flex items-center md:w-64 md:h-40" v-else>
                                    <img :src="selected[2].preview">
                                </div>
                            <div class="grid col-span-1 row-span-1 bg-slate-800 w-36 h-40 md:w-64 md:h-40 rounded-xl" v-if="JSON.stringify(selected[3]) === '{}'">
                                <div class="flex justify-center self-center">
                                    <button @click="togglePopup('landscape',3)" class="px-5 py-3 bg-yellow-300 rounded-lg text-sm lg:text-lg">Select</button>
                                </div>
                            </div>
                                <div class="flex items-center md:w-64 md:h-40" v-else>
                                    <img :src="selected[3].preview">
                                </div>
                        </div>
                    </div>
                    <div class="flex justify-center" v-else>
                        <p>Not Selected</p>
                    </div>
                </div>
            </div>
        </div>
        <!-- VDO Layout -->
        <div class="h-auto lg:flex lg:justify-center lg:items-center mx-3">
            <div class="grid grid-cols-4 grid-rows-2 gap-2 md:gap-1 md:flex p-3 ">
                <div class="lg:ml-2"
                v-for="(img,index) in imgLayout" :key="index" @click="SelectLayout2(img,index)">
                    <img :src="img.url">
                </div>
            </div>
        </div>
        <!-- Btn to next -->
        <div class="flex justify-center">
            <button class="next bg-yellow-300 p-3 rounded-lg hover:scale-90 linear text-md md:text-lg">Next Process</button>
        </div>
    </div>
</template>

<script setup>
import { ref, reactive, computed, onMounted } from 'vue';

const openMenu = ref(false);
const toggleModal = ref(false);
const layoutSelect = ref(false);
const isLayout = ref(8);
const layoutnum = ref(0);
const loginStatus = ref(true);
const vdo = ref('Default');
const searchValue = ref('');
const callLayout = ref('');
const items = ref([]);
const items_p = ref([]);
const selected = ref([]);
const collected = ref('');
const showpic = ref(false);
const nextModal = ref(false);

const imgLayout = reactive([
  {
    url: "https://media04.tetraserver.com/uploads/layout/2_01_NUM.png",
    need: 2,
  },
  {
    url: "https://media04.tetraserver.com/uploads/layout/2_02_NUM.png",
    need: 2,
  },
  {
    url: "https://media04.tetraserver.com/uploads/layout/2_03_NUM.png",
    need: 2,
  },
  {
    url: "https://media04.tetraserver.com/uploads/layout/2_04_NUM.png",
    need: 2,
  },
  {
    url: "https://media04.tetraserver.com/uploads/layout/3_01_NUM.png",
    need: 3,
  },
  {
    url: "https://media04.tetraserver.com/uploads/layout/3_02_NUM.png",
    need: 3,
  },
  {
    url: "https://media04.tetraserver.com/uploads/layout/3_03_NUM.png",
    need: 3,
  },
  {
    url: "https://media04.tetraserver.com/uploads/layout/4_01_NUM.png",
    need: 4,
  },
]);

const openNav = () => {
  openMenu.value = !openMenu.value;
  console.log('OpenNav');
};

const closeBtn = () => {
  toggleModal.value = !toggleModal.value;
};

const togglePopup = (obj, index) => {
  if (obj === 'portait') {
    vdo.value = 'portait';
  }
  if (obj === 'landscape') {
    vdo.value = 'landscape';
  }
  callLayout.value = index;
  toggleModal.value = !toggleModal.value;
};

const addVideo = () => {
  let check = false;
  selected.value.forEach(el => {
    if (el.url === collected.value.url) {
      return (check = true);
    }
  });

  if (collected.value === '') {
    alert('choose Video');
  } else if (check) {
    alert('Same VDO');
  } else {
    selected.value[callLayout.value] = collected.value;
    showpic.value = true;
    toggleModal.value = !toggleModal.value;
    collected.value = '';
    searchValue.value = '';
    if (selected.value.length === layoutnum.value) {
      nextModal.value = !nextModal.value;
    }
  }
};

const SelectVDO = (index) => {
  if (vdo.value === 'portait') {
    collected.value = itemListP.value[index];
  }
  if (vdo.value === 'landscape') {
    collected.value = itemList.value[index];
  }
};

const SelectLayout2 = (img, index) => {
  if (selected.value !== []) {
    selected.value = [];
  }
  layoutSelect.value = true;
  isLayout.value = index;
  layoutnum.value = img.need;

  for (let i = 0; i < layoutnum.value; i++) {
    selected.value.push({});
  }
};

const itemList = computed(() => {
  if (searchValue.value.trim().length > 0) {
    return items.value.filter(
      (item) =>
        item.video_title.toLowerCase().includes(searchValue.value.trim().toLowerCase()) ||
        item.music_title.toLowerCase().includes(searchValue.value.trim().toLowerCase())
    );
  }
  return items.value;
});

const itemListP = computed(() => {
  if (searchValue.value.trim().length > 0) {
    return items_p.value.filter(
      (item_p) =>
        item_p.video_title.toLowerCase().includes(searchValue.value.trim().toLowerCase()) ||
        item_p.music_title.toLowerCase().includes(searchValue.value.trim().toLowerCase())
    );
  }
  return items_p.value;
});

const fetchItems = () => {
  fetch('https://fuzik03.tetraserver.com/plays_l/')
    .then((res) => res.json())
    .then((result) => {
      items.value = result;
    });

  fetch('https://fuzik03.tetraserver.com/plays_p/')
    .then((res) => res.json())
    .then((result) => {
      items_p.value = result;
    });
};

onMounted(fetchItems);


// export default {
//     props: ['video_title','url','preview','music_title'],
//     name: "modal",
//     data() {
//         return {
//             openMenu: false,
//             toggleModal: false,
//             layoutSelect: false,
//             isLayout: 8,
//             layoutnum: 0,
//             loginStatus: true,
//             vdo: 'Default',
//             searchValue: '',
//             callLayout: '',
//             items: [],
//             items_p: [],
//             selected: [],
//             collected: '',
//             imgLayout: [
//                 {
//                     "url": "https://media04.tetraserver.com/uploads/layout/2_01_NUM.png",
//                     "need": 2,
//                 },
//                 {
//                     "url": "https://media04.tetraserver.com/uploads/layout/2_02_NUM.png",
//                     "need": 2,
//                 },
//                 {
//                     "url": "https://media04.tetraserver.com/uploads/layout/2_03_NUM.png",
//                     "need": 2,
//                 },
//                 {
//                     "url": "https://media04.tetraserver.com/uploads/layout/2_04_NUM.png",
//                     "need": 2,
//                 },
//                 {
//                     "url": "https://media04.tetraserver.com/uploads/layout/3_01_NUM.png",
//                     "need": 3,
//                 },
//                 {
//                     "url": "https://media04.tetraserver.com/uploads/layout/3_02_NUM.png",
//                     "need": 3,
//                 },
//                 {
//                     "url": "https://media04.tetraserver.com/uploads/layout/3_03_NUM.png",
//                     "need": 3,
//                 },
//                 {
//                     "url": "https://media04.tetraserver.com/uploads/layout/4_01_NUM.png",
//                     "need": 4,
//                 },
//             ],
//         };
//     },
//     methods: {
//         openNav() {
//             this.openMenu = !this.openMenu;
//             console.log('OpenNav');
//         },
//         closeBtn() {
//             this.toggleModal = !this.toggleModal;
//         },
//         togglePopup(obj,index) {
//             if (obj == 'portait') {
//                 this.vdo = 'portait'
//             }
//             if (obj == 'landscape'){
//                 this.vdo = 'landscape'
//             }
//             this.callLayout = index;
//             this.toggleModal = !this.toggleModal;
//         },
//         addVideo() {
//             let check = false;
//             this.selected.forEach(el => {
//                 if(el.url == this.collected.url){
//                     return check = true;
//                 }
//             });

//             if(this.collected == ''){
//                 alert('choose Video');
//             } else if (check){
//                 alert('Same VDO');
//             }
//             else {
//                 this.selected[this.callLayout] = this.collected;
//                 this.showpic = true;
//                 this.toggleModal = !this.toggleModal;
//                 this.collected = '';
//                 this.searchValue = '';
//                 if (this.selected.length == this.layoutnum) {
//                     this.nextModal = !this.nextModal;                    
//                 }
//             }
//         },
//         // Select Video
//         SelectVDO(index){
//             if (this.vdo == 'portait') {
//                 this.collected = this.itemListP[index];
//             }
//             if (this.vdo == 'landscape') {
//                 this.collected = this.itemList[index]; 
//             }
//         },
//         // Selected Layout
//         SelectLayout2(img,index) {
//             if (this.selected != []) {
//                 this.selected = [];
//             }
//             this.layoutSelect = true;
//             this.isLayout = index;
//             this.layoutnum = img.need;

//             for (let i = 0; i < this.layoutnum; i++) {
//                 this.selected.push({});
//             }
//         },
//     },
//     computed: {
//         itemList() {
//                 if (this.searchValue.trim().length > 0){
//                     return this.items.filter((item) => 
//                     item.video_title.toLowerCase().includes(this.searchValue.trim().toLowerCase())
//                     || item.music_title.toLowerCase().includes(this.searchValue.trim().toLowerCase()))
//                 }
//                 return this.items
//             },
//         itemListP() {
//             if (this.searchValue.trim().length > 0){
//                     return this.items_p.filter((item_p) => 
//                     item_p.video_title.toLowerCase().includes(this.searchValue.trim().toLowerCase())
//                     || item_p.music_title.toLowerCase().includes(this.searchValue.trim().toLowerCase()))
//                 }
//             return this.items_p
//         }
//     },
//     created() {
//         fetch('https://fuzik03.tetraserver.com/plays_l/')
//         .then(res => res.json())
//         .then((result) => {
//             this.items = result
//         }),
//         fetch('https://fuzik03.tetraserver.com/plays_p/')
//         .then(res => res.json())
//         .then((result) => {
//             this.items_p = result
//         })
//     }
// };
</script>

<style type="text/tailwindcss">
#popup{
    background-color: rgba(0, 0, 0, .4);
}
.color{
    fill:yellow;
}
.icon{
    fill:yellow;
}
.Navmenu{
    background-color: rgba(0, 0, 0, .4);
}
</style>