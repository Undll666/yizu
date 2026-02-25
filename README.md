<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>数智社区小程序</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <style>
        /* 隐藏滚动条但保留滚动功能 */
        ::-webkit-scrollbar { display: none; }
        .hide-scroll { -ms-overflow-style: none; scrollbar-width: none; }
        
        /* 页面切换的滑动动画 */
        .slide-enter-active, .slide-leave-active {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: absolute;
            width: 100%;
            height: 100%;
        }
        .slide-enter-from { transform: translateX(100%); opacity: 0; }
        .slide-leave-to { transform: translateX(-100%); opacity: 0; }
        
        /* 返回动画 */
        .slide-back-enter-active, .slide-back-leave-active {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: absolute;
            width: 100%;
            height: 100%;
        }
        .slide-back-enter-from { transform: translateX(-100%); opacity: 0; }
        .slide-back-leave-to { transform: translateX(100%); opacity: 0; }
    </style>
</head>
<body class="bg-gray-200 flex items-center justify-center min-h-screen font-sans">

    <div id="app" class="relative w-full max-w-[390px] h-[844px] bg-gray-50 overflow-hidden sm:rounded-[3rem] sm:border-[10px] sm:border-gray-900 shadow-2xl flex flex-col">
        
        <transition :name="transitionName">
            
            <div v-if="currentPage === 'home'" class="absolute inset-0 flex flex-col hide-scroll overflow-y-auto bg-gray-50 pb-20">
                <div class="px-5 pt-12 pb-4 bg-gradient-to-r from-red-600 to-orange-500 text-white rounded-b-3xl shadow-md">
                    <div class="flex justify-between items-center mb-4">
                        <div class="flex items-center space-x-1 text-sm font-medium">
                            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                            <span>越西县·易地搬迁社区</span>
                        </div>
                        <div class="w-8 h-8 bg-white/20 rounded-full flex items-center justify-center">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"></path></svg>
                        </div>
                    </div>
                    <h1 class="text-2xl font-bold tracking-wider">数智大脑</h1>
                    <p class="text-xs text-orange-100 mt-1 opacity-90">非遗产业产销协同智治平台</p>
                </div>

                <div class="px-5 -mt-6 relative z-10">
                    <div class="bg-white rounded-2xl p-4 shadow-sm border border-gray-100 flex justify-between items-center">
                        <div class="text-center">
                            <p class="text-xs text-gray-500 mb-1">本周订单</p>
                            <p class="text-xl font-bold text-gray-800">128<span class="text-xs font-normal"> 件</span></p>
                        </div>
                        <div class="w-px h-8 bg-gray-200"></div>
                        <div class="text-center">
                            <p class="text-xs text-gray-500 mb-1">在线绣娘</p>
                            <p class="text-xl font-bold text-gray-800">42<span class="text-xs font-normal"> 人</span></p>
                        </div>
                        <div class="w-px h-8 bg-gray-200"></div>
                        <div class="text-center">
                            <p class="text-xs text-gray-500 mb-1">增收金额</p>
                            <p class="text-xl font-bold text-red-500">2.4<span class="text-xs font-normal"> w</span></p>
                        </div>
                    </div>
                </div>

                <div class="px-5 mt-6 space-y-4">
                    <h2 class="text-base font-bold text-gray-800 mb-2">核心工作台</h2>
                    
                    <div @click="goTo('production')" class="bg-gradient-to-br from-blue-50 to-indigo-50 rounded-2xl p-4 shadow-sm border border-blue-100 flex items-center justify-between active:scale-95 transition transform">
                        <div class="flex-1">
                            <span class="inline-block px-2 py-1 bg-blue-100 text-blue-600 text-[10px] font-bold rounded mb-2">生产管理</span>
                            <h3 class="text-lg font-bold text-gray-800">柔性智能分单</h3>
                            <p class="text-xs text-gray-500 mt-1 line-clamp-1">基于空闲时间与技能的订单解构池</p>
                        </div>
                        <div class="w-12 h-12 bg-blue-500 text-white rounded-full flex items-center justify-center shadow-inner">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-6 9l2 2 4-4"></path></svg>
                        </div>
                    </div>

                    <div @click="goTo('qc')" class="bg-gradient-to-br from-emerald-50 to-teal-50 rounded-2xl p-4 shadow-sm border border-emerald-100 flex items-center justify-between active:scale-95 transition transform">
                        <div class="flex-1">
                            <span class="inline-block px-2 py-1 bg-emerald-100 text-emerald-600 text-[10px] font-bold rounded mb-2">质量赋能</span>
                            <h3 class="text-lg font-bold text-gray-800">AI视觉质检教学</h3>
                            <p class="text-xs text-gray-500 mt-1 line-clamp-1">工序打卡 / 瑕疵识别 / 触发式微课</p>
                        </div>
                        <div class="w-12 h-12 bg-emerald-500 text-white rounded-full flex items-center justify-center shadow-inner">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 9a2 2 0 012-2h.93a2 2 0 001.664-.89l.812-1.22A2 2 0 0110.07 4h3.86a2 2 0 011.664.89l.812 1.22A2 2 0 0018.07 7H19a2 2 0 012 2v9a2 2 0 01-2 2H5a2 2 0 01-2-2V9z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 13a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                        </div>
                    </div>

                    <div @click="goTo('sales')" class="bg-gradient-to-br from-rose-50 to-pink-50 rounded-2xl p-4 shadow-sm border border-rose-100 flex items-center justify-between active:scale-95 transition transform">
                        <div class="flex-1">
                            <span class="inline-block px-2 py-1 bg-rose-100 text-rose-600 text-[10px] font-bold rounded mb-2">产销一体</span>
                            <h3 class="text-lg font-bold text-gray-800">非遗文创商城</h3>
                            <p class="text-xs text-gray-500 mt-1 line-clamp-1">双轨交易展示 / 生产透明溯源</p>
                        </div>
                        <div class="w-12 h-12 bg-rose-500 text-white rounded-full flex items-center justify-center shadow-inner">
                            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"></path></svg>
                        </div>
                    </div>
                </div>
            </div>

            <div v-else-if="currentPage === 'production'" class="absolute inset-0 flex flex-col bg-gray-50 z-20">
                <div class="pt-12 pb-3 px-4 bg-white flex items-center shadow-sm sticky top-0 z-30">
                    <button @click="goBack" class="p-2 -ml-2 text-gray-600 active:bg-gray-100 rounded-full">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path></svg>
                    </button>
                    <h2 class="flex-1 text-center text-lg font-bold text-gray-800 pr-8">任务大厅</h2>
                </div>
                
                <div class="flex-1 overflow-y-auto px-4 py-4 hide-scroll">
                    <div class="bg-blue-50 text-blue-800 p-3 rounded-xl text-sm mb-4 border border-blue-100 flex items-start">
                        <svg class="w-5 h-5 mr-2 mt-0.5 flex-shrink-0" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd"></path></svg>
                        <div>系统已识别您在 <strong>14:00-16:00</strong> 有微空闲时段，为您智能匹配以下微任务。</div>
                    </div>

                    <h3 class="font-bold text-gray-800 mb-3">为您推荐的任务池</h3>
                    <div class="bg-white p-4 rounded-2xl shadow-sm mb-3 border border-gray-100">
                        <div class="flex justify-between items-start mb-2">
                            <span class="bg-orange-100 text-orange-600 text-[10px] px-2 py-0.5 rounded font-bold">潮流文创线</span>
                            <span class="text-lg font-bold text-red-500">¥ 8.50</span>
                        </div>
                        <h4 class="font-bold text-gray-800 text-base mb-1">棉花娃娃：基础裁剪与拼合</h4>
                        <div class="flex space-x-2 text-xs text-gray-500 mb-4">
                            <span class="bg-gray-100 px-2 py-1 rounded">预计 20 分钟</span>
                            <span class="bg-gray-100 px-2 py-1 rounded">难度：初级</span>
                        </div>
                        <button class="w-full bg-indigo-600 text-white font-bold py-2.5 rounded-xl active:bg-indigo-700">一键接单</button>
                    </div>

                    <div class="bg-white p-4 rounded-2xl shadow-sm mb-3 border border-gray-100 opacity-80">
                        <div class="flex justify-between items-start mb-2">
                            <span class="bg-purple-100 text-purple-600 text-[10px] px-2 py-0.5 rounded font-bold">高端定制线</span>
                            <span class="text-lg font-bold text-red-500">¥ 45.00</span>
                        </div>
                        <h4 class="font-bold text-gray-800 text-base mb-1">彝族银饰：领口图腾刺绣</h4>
                        <div class="flex space-x-2 text-xs text-gray-500 mb-4">
                            <span class="bg-gray-100 px-2 py-1 rounded">预计 1.5 小时</span>
                            <span class="bg-gray-100 px-2 py-1 rounded text-red-500">需高级技法</span>
                        </div>
                        <button class="w-full bg-gray-200 text-gray-500 font-bold py-2.5 rounded-xl cursor-not-allowed">等级不足，无法接单</button>
                    </div>
                </div>
            </div>

            <div v-else-if="currentPage === 'qc'" class="absolute inset-0 flex flex-col bg-gray-50 z-20">
                <div class="pt-12 pb-3 px-4 bg-white flex items-center shadow-sm sticky top-0 z-30">
                    <button @click="goBack" class="p-2 -ml-2 text-gray-600 active:bg-gray-100 rounded-full">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path></svg>
                    </button>
                    <h2 class="flex-1 text-center text-lg font-bold text-gray-800 pr-8">AI 节点质检</h2>
                </div>
                
                <div class="flex-1 overflow-y-auto px-4 py-4 hide-scroll">
                    <div class="bg-gray-800 rounded-2xl h-64 flex flex-col items-center justify-center text-white relative overflow-hidden shadow-inner mb-6">
                        <div class="absolute inset-0 opacity-20 bg-[url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMCIgaGVpZ2h0PSIyMCI+PHBhdGggZD0iTTAgMGgyMHYyMEgwem0xMCAxMGgxMHYxMEgxMHoiIGZpbGw9IiNmZmYiIGZpbGwtb3BhY2l0eT0iLjA1Ii8+PC9zdmc+')]"></div>
                        <svg class="w-12 h-12 mb-3 text-gray-400 z-10" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 9a2 2 0 012-2h.93a2 2 0 001.664-.89l.812-1.22A2 2 0 0110.07 4h3.86a2 2 0 011.664.89l.812 1.22A2 2 0 0018.07 7H19a2 2 0 012 2v9a2 2 0 01-2 2H5a2 2 0 01-2-2V9z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 13a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                        <p class="z-10 font-medium tracking-wide">请将半成品置于取景框内</p>
                        <button class="mt-4 px-6 py-2 bg-emerald-500 rounded-full font-bold z-10 active:bg-emerald-600 shadow-lg">点击拍照比对</button>
                    </div>

                    <h3 class="font-bold text-gray-800 mb-3">系统初筛反馈</h3>
                    <div class="bg-white p-4 rounded-2xl shadow-sm border-l-4 border-yellow-400">
                        <div class="flex items-center text-yellow-600 font-bold mb-2">
                            <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M8.257 3.099c.765-1.36 2.722-1.36 3.486 0l5.58 9.92c.75 1.334-.213 2.98-1.742 2.98H4.42c-1.53 0-2.493-1.646-1.743-2.98l5.58-9.92zM11 13a1 1 0 11-2 0 1 1 0 012 0zm-1-8a1 1 0 00-1 1v3a1 1 0 002 0V6a1 1 0 00-1-1z" clip-rule="evenodd"></path></svg>
                            识别到轻微瑕疵
                        </div>
                        <p class="text-sm text-gray-600 mb-2">右侧袖口处存在 <span class="font-bold text-red-500">边缘跳针</span>，不符合标准图谱库走线要求。</p>
                        
                        <div class="mt-4 p-3 bg-indigo-50 rounded-xl border border-indigo-100">
                            <p class="text-xs font-bold text-indigo-800 mb-2">💡 触发式技能提升</p>
                            <div class="flex items-center bg-white p-2 rounded-lg shadow-sm">
                                <div class="w-10 h-10 bg-indigo-200 rounded flex items-center justify-center mr-3">
                                    <svg class="w-5 h-5 text-indigo-600" fill="currentColor" viewBox="0 0 20 20"><path d="M2 6a2 2 0 012-2h6a2 2 0 012 2v8a2 2 0 01-2 2H4a2 2 0 01-2-2V6zM14.553 7.106A1 1 0 0014 8v4a1 1 0 00.553.894l2 1A1 1 0 0018 13V7a1 1 0 00-1.447-.894l-2 1z"></path></svg>
                                </div>
                                <div>
                                    <p class="text-xs font-bold text-gray-800">微课：如何规避厚料跳针</p>
                                    <p class="text-[10px] text-gray-500">时长 01:20 · 建议返工前观看</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div v-else-if="currentPage === 'sales'" class="absolute inset-0 flex flex-col bg-gray-50 z-20">
                <div class="pt-12 pb-3 px-4 bg-white flex items-center shadow-sm sticky top-0 z-30">
                    <button @click="goBack" class="p-2 -ml-2 text-gray-600 active:bg-gray-100 rounded-full">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path></svg>
                    </button>
                    <div class="flex-1 ml-2 bg-gray-100 rounded-full px-4 py-1.5 flex items-center">
                        <svg class="w-4 h-4 text-gray-400 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path></svg>
                        <span class="text-xs text-gray-400">搜索非遗文创 / 彝族服饰</span>
                    </div>
                </div>
                
                <div class="flex-1 overflow-y-auto px-4 py-4 hide-scroll bg-gray-100">
                    <div class="bg-gradient-to-r from-red-800 to-red-600 rounded-2xl p-4 text-white shadow-md mb-4 flex justify-between items-center">
                        <div>
                            <h3 class="font-bold text-lg mb-1">大凉山·指尖上的非遗</h3>
                            <p class="text-xs text-red-100">每一件都由社区绣娘纯手工缝制</p>
                        </div>
                        <div class="w-12 h-12 bg-white/20 rounded-full flex items-center justify-center">
                            <span class="text-xs font-bold">保真</span>
                        </div>
                    </div>

                    <div class="grid grid-cols-2 gap-3">
                        <div class="bg-white rounded-xl overflow-hidden shadow-sm">
                            <div class="h-32 bg-gray-200 flex items-center justify-center relative">
                                <span class="text-gray-400 text-xs">文创产品实拍图</span>
                                <span class="absolute bottom-1 right-1 bg-black/50 text-white text-[9px] px-1.5 py-0.5 rounded">可溯源</span>
                            </div>
                            <div class="p-2">
                                <h4 class="text-sm font-bold text-gray-800 line-clamp-1">彝风棉花娃娃服饰套装</h4>
                                <div class="flex justify-between items-center mt-2">
                                    <span class="text-red-500 font-bold text-sm">¥ 39.9</span>
                                    <button class="bg-red-500 text-white text-[10px] px-2 py-1 rounded-full">购买</button>
                                </div>
                            </div>
                        </div>

                        <div class="bg-white rounded-xl overflow-hidden shadow-sm">
                            <div class="h-32 bg-amber-100 flex items-center justify-center relative">
                                <span class="text-amber-800 text-xs font-bold">高端定制图腾展示</span>
                            </div>
                            <div class="p-2">
                                <h4 class="text-sm font-bold text-gray-800 line-clamp-1">纯手工银饰图腾披风</h4>
                                <div class="flex justify-between items-center mt-2">
                                    <span class="text-red-500 font-bold text-sm">¥ 599.0</span>
                                    <button class="border border-red-500 text-red-500 text-[10px] px-2 py-1 rounded-full">集采洽谈</button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="mt-6 bg-white p-4 rounded-2xl shadow-sm">
                        <h3 class="font-bold text-gray-800 text-sm mb-4">订单溯源透明化演示</h3>
                        <div class="relative border-l-2 border-red-200 ml-2 space-y-4">
                            <div class="relative pl-4">
                                <div class="absolute w-3 h-3 bg-red-500 rounded-full -left-[7px] top-1"></div>
                                <p class="text-xs font-bold text-gray-800">订单已支付，自动拆解派单</p>
                                <p class="text-[10px] text-gray-400">10:00</p>
                            </div>
                            <div class="relative pl-4">
                                <div class="absolute w-3 h-3 bg-red-500 rounded-full -left-[7px] top-1"></div>
                                <p class="text-xs font-bold text-gray-800">【高级绣娘】李阿姨 正在缝制</p>
                                <p class="text-[10px] text-gray-400">14:30</p>
                            </div>
                            <div class="relative pl-4">
                                <div class="absolute w-3 h-3 bg-gray-300 rounded-full -left-[7px] top-1"></div>
                                <p class="text-xs text-gray-400">等待 AI 视觉质检...</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
        </transition>

        <div class="absolute bottom-1 left-0 right-0 h-1.5 flex justify-center z-50 pointer-events-none">
            <div class="w-1/3 bg-gray-800 rounded-full opacity-20"></div>
        </div>
    </div>

    <script>
        const { createApp, ref } = Vue;
        
        createApp({
            setup() {
                const currentPage = ref('home');
                const transitionName = ref('slide'); // 用于判断前进还是后退动画

                const goTo = (page) => {
                    transitionName.ref = 'slide';
                    currentPage.value = page;
                };

                const goBack = () => {
                    transitionName.value = 'slide-back';
                    currentPage.value = 'home';
                };

                return {
                    currentPage,
                    transitionName,
                    goTo,
                    goBack
                }
            }
        }).mount('#app');
    </script>
</body>
</html>
