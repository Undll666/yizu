<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>易地搬迁社区产业“数智大脑”</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <style>
        /* 简单的过渡动画 */
        .fade-enter-active, .fade-leave-active { transition: opacity 0.3s ease; }
        .fade-enter-from, .fade-leave-to { opacity: 0; }
    </style>
</head>
<body class="bg-gray-50 text-gray-800 font-sans">
    <div id="app" class="flex h-screen overflow-hidden">

        <aside class="w-64 bg-indigo-900 text-white flex flex-col shadow-xl">
            <div class="p-6 text-center border-b border-indigo-800">
                <h1 class="text-2xl font-bold tracking-wider">数智大脑</h1>
                <p class="text-xs text-indigo-300 mt-2">社区产业协同治理中枢</p>
            </div>
            <nav class="flex-1 px-4 py-6 space-y-2">
                <button @click="currentTab = 'production'" :class="{'bg-indigo-700': currentTab === 'production'}" class="w-full flex items-center px-4 py-3 rounded-lg hover:bg-indigo-600 transition">
                    <span class="font-medium">生产端：智能分单</span>
                </button>
                <button @click="currentTab = 'qc'" :class="{'bg-indigo-700': currentTab === 'qc'}" class="w-full flex items-center px-4 py-3 rounded-lg hover:bg-indigo-600 transition">
                    <span class="font-medium">品控端：AI质检与教学</span>
                </button>
                <button @click="currentTab = 'sales'" :class="{'bg-indigo-700': currentTab === 'sales'}" class="w-full flex items-center px-4 py-3 rounded-lg hover:bg-indigo-600 transition">
                    <span class="font-medium">销售端：产销与溯源</span>
                </button>
            </nav>
            <div class="p-4 text-xs text-indigo-400 text-center border-t border-indigo-800">
                端云协同架构 Demo
            </div>
        </aside>

        <main class="flex-1 overflow-y-auto p-8 relative">
            <transition name="fade" mode="out-in">
                
                <div v-if="currentTab === 'production'" key="production" class="space-y-6">
                    <h2 class="text-3xl font-bold text-gray-800 border-l-4 border-indigo-600 pl-4">基于“评估-解构-匹配”的柔性分单系统</h2>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-100">
                            <h3 class="text-xl font-semibold mb-4 text-indigo-800">1. 订单任务解构 (微任务池)</h3>
                            <div class="space-y-3">
                                <div class="p-3 bg-blue-50 rounded-lg border border-blue-100 flex justify-between items-center">
                                    <div>
                                        <span class="text-xs font-bold bg-blue-200 text-blue-800 px-2 py-1 rounded mr-2">潮流线</span>
                                        <span class="font-medium">棉花娃娃：基础机缝拼接</span>
                                    </div>
                                    <span class="text-sm text-gray-500">预估耗时: 15分钟</span>
                                </div>
                                <div class="p-3 bg-purple-50 rounded-lg border border-purple-100 flex justify-between items-center">
                                    <div>
                                        <span class="text-xs font-bold bg-purple-200 text-purple-800 px-2 py-1 rounded mr-2">高端线</span>
                                        <span class="font-medium">彝族图腾：核心刺绣部分</span>
                                    </div>
                                    <span class="text-sm text-gray-500">预估耗时: 120分钟</span>
                                </div>
                            </div>
                        </div>

                        <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-100">
                            <h3 class="text-xl font-semibold mb-4 text-green-800">2. 算法驱动智能派发</h3>
                            <div class="space-y-4">
                                <div class="flex items-start space-x-4 p-4 bg-gray-50 rounded-lg border border-gray-200">
                                    <div class="w-12 h-12 bg-green-100 text-green-600 rounded-full flex items-center justify-center font-bold">匹配</div>
                                    <div>
                                        <h4 class="font-bold text-gray-800">任务已派发：基础机缝拼接</h4>
                                        <p class="text-sm text-gray-600 mt-1">接收人：王阿姨 (初级技能)</p>
                                        <p class="text-xs text-green-600 mt-1">匹配依据：可用“微空闲”时段 14:00-16:00，视力状况良好</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div v-if="currentTab === 'qc'" key="qc" class="space-y-6">
                    <h2 class="text-3xl font-bold text-gray-800 border-l-4 border-indigo-600 pl-4">计算机视觉质检与辅助教学闭环</h2>
                    
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-100">
                        <h3 class="text-xl font-semibold mb-4">关键节点图像上传与反馈</h3>
                        
                        <div class="flex flex-col md:flex-row gap-8">
                            <div class="flex-1 border-2 border-dashed border-gray-300 rounded-xl p-8 text-center bg-gray-50 flex flex-col justify-center items-center">
                                <div class="w-24 h-24 bg-gray-200 rounded-lg mb-4 flex items-center justify-center text-gray-400">
                                    [半成品照片]
                                </div>
                                <button class="px-6 py-2 bg-indigo-600 text-white rounded-lg hover:bg-indigo-700 transition">一键拍照打卡检验</button>
                                <p class="text-xs text-gray-500 mt-2">系统将自动调用云端标准图谱库进行比对</p>
                            </div>

                            <div class="flex-1 space-y-4">
                                <div class="p-4 bg-red-50 border border-red-200 rounded-lg">
                                    <div class="flex items-center text-red-700 font-bold mb-2">
                                        <svg class="w-5 h-5 mr-2" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM8.707 7.293a1 1 0 00-1.414 1.414L8.586 10l-1.293 1.293a1 1 0 101.414 1.414L10 11.414l1.293 1.293a1 1 0 001.414-1.414L11.414 10l1.293-1.293a1 1 0 00-1.414-1.414L10 8.586 8.707 7.293z" clip-rule="evenodd"></path></svg>
                                        质检初筛报告：发现瑕疵
                                    </div>
                                    <p class="text-sm text-gray-700">问题标记：<span class="bg-yellow-200 text-yellow-800 px-1 rounded">边缘跳针</span></p>
                                    <p class="text-xs text-gray-500 mt-1">返修建议：请拆解最后两厘米线迹，调紧缝纫机面线张力重新缝制。</p>
                                </div>

                                <div class="p-4 bg-yellow-50 border border-yellow-200 rounded-lg shadow-sm border-l-4 border-l-yellow-500">
                                    <h4 class="font-bold text-yellow-800 mb-1">触发式辅助教学提醒</h4>
                                    <p class="text-sm text-gray-700">系统检测到该节点高频错误。已为您定向推送微课：</p>
                                    <a href="#" class="inline-block mt-2 text-indigo-600 font-medium text-sm hover:underline">▶ 视频教程：如何避免棉布厚料的边缘跳针问题</a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div v-if="currentTab === 'sales'" key="sales" class="space-y-6">
                    <h2 class="text-3xl font-bold text-gray-800 border-l-4 border-indigo-600 pl-4">产销一体化与数字溯源网络</h2>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="bg-white rounded-xl shadow-sm border border-gray-100 overflow-hidden relative">
                            <div class="h-32 bg-gradient-to-r from-pink-100 to-rose-100 flex items-center justify-center relative">
                                <span class="text-rose-800 font-bold text-lg">潮流文创专区</span>
                                <span class="absolute top-2 right-2 bg-white text-xs px-2 py-1 rounded-full text-rose-600 font-bold">轻量级</span>
                            </div>
                            <div class="p-4">
                                <h4 class="font-bold">民族风棉花娃娃服饰套装</h4>
                                <p class="text-sm text-gray-500 mt-1">已接入自动拆解流，支持小批量定制。</p>
                                <button class="mt-4 w-full py-2 bg-gray-900 text-white rounded hover:bg-gray-800 text-sm">模拟下单 (触发生产指令)</button>
                            </div>
                        </div>
                        <div class="bg-white rounded-xl shadow-sm border border-gray-100 overflow-hidden relative">
                            <div class="h-32 bg-gradient-to-r from-amber-100 to-orange-100 flex items-center justify-center relative">
                                <span class="text-amber-800 font-bold text-lg">高端非遗定制展厅</span>
                                <span class="absolute top-2 right-2 bg-white text-xs px-2 py-1 rounded-full text-amber-600 font-bold">高附加值</span>
                            </div>
                            <div class="p-4">
                                <h4 class="font-bold">传统手工彝族图腾银饰绣衣</h4>
                                <p class="text-sm text-gray-500 mt-1">由系统高信用熟练工匠承接，100%手工溯源。</p>
                                <button class="mt-4 w-full py-2 border-2 border-gray-900 text-gray-900 rounded hover:bg-gray-50 text-sm">发起集采打样 / 意向洽谈</button>
                            </div>
                        </div>
                    </div>

                    <div class="bg-white p-6 rounded-xl shadow-sm border border-gray-100">
                        <h3 class="text-xl font-semibold mb-6">消费者视角：生产进度透明化与溯源</h3>
                        <div class="relative border-l-2 border-indigo-200 ml-3 space-y-8">
                            <div class="relative pl-6">
                                <div class="absolute w-4 h-4 bg-indigo-600 rounded-full -left-[9px] top-1"></div>
                                <h4 class="font-bold text-gray-800">订单已支付，系统自动解构派单</h4>
                                <p class="text-xs text-gray-500">2026-03-01 10:00</p>
                            </div>
                            <div class="relative pl-6">
                                <div class="absolute w-4 h-4 bg-indigo-600 rounded-full -left-[9px] top-1"></div>
                                <h4 class="font-bold text-gray-800">李阿姨 (高级绣娘) 正在缝制图腾部件</h4>
                                <p class="text-xs text-gray-500">2026-03-02 14:30</p>
                            </div>
                            <div class="relative pl-6">
                                <div class="absolute w-4 h-4 bg-green-500 rounded-full -left-[9px] top-1"></div>
                                <h4 class="font-bold text-gray-800">AI视觉质检通过</h4>
                                <p class="text-xs text-gray-500">2026-03-04 09:15 | 走线平整，无色差</p>
                            </div>
                            <div class="relative pl-6">
                                <div class="absolute w-4 h-4 bg-gray-300 rounded-full -left-[9px] top-1"></div>
                                <h4 class="font-bold text-gray-400">社区物流集散点已核销揽收，准备发货</h4>
                                <p class="text-xs text-gray-400">等待执行...</p>
                            </div>
                        </div>
                    </div>
                </div>
            </transition>
        </main>
    </div>

    <script>
        const { createApp, ref } = Vue;
        createApp({
            setup() {
                // 默认显示第一个 Tab：生产管理
                const currentTab = ref('production'); 
                return {
                    currentTab
                }
            }
        }).mount('#app');
    </script>
</body>
</html>
