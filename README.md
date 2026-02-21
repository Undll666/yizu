<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>越西县易地搬迁社区产业“数智大脑”</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" rel="stylesheet">
    <style>
        body { background-color: #0f0f0f; color: #fff; font-family: "PingFang SC", "Microsoft YaHei", sans-serif; overflow-x: hidden; }
        .yi-red { background-color: #C8102E; }
        .yi-yellow { color: #FFCD00; }
        .glass-card { background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(10px); border: 1px solid rgba(255, 255, 255, 0.1); border-radius: 12px; }
        .nav-btn { cursor: pointer; transition: all 0.3s; border-bottom: 2px solid transparent; }
        .nav-btn:hover, .nav-btn.active { color: #C8102E; border-bottom: 2px solid #C8102E; }
        .tab-content { display: none; }
        .tab-content.active { display: block; animation: fadeIn 0.8s; }
        .progress-line::before { content: ''; position: absolute; top: 50%; left: 0; right: 0; height: 2px; background: #333; z-index: -1; }
    </style>
</head>
<body>

    <nav class="flex items-center justify-between px-8 py-4 border-b border-gray-800 bg-black sticky top-0 z-50">
        <div class="flex items-center space-x-3">
            <div class="w-10 h-10 yi-red rounded-full flex items-center justify-center font-bold text-xl">越</div>
            <h1 class="text-xl font-bold tracking-widest">数智大脑 <span class="yi-yellow text-sm font-normal">Smarter Community v2.0</span></h1>
        </div>
        <div class="flex space-x-8 text-sm font-medium">
            <div onclick="showTab('admin')" class="nav-btn active py-2" id="btn-admin">生产管理中枢</div>
            <div onclick="showTab('market')" class="nav-btn py-2" id="btn-market">文化展示门户</div>
            <div onclick="showTab('trace')" class="nav-btn py-2" id="btn-trace">透明溯源进度</div>
        </div>
        <div class="px-4 py-1 rounded-full border border-yellow-600 text-yellow-600 text-xs">越西县·易地搬迁社区</div>
    </nav>

    <main class="p-6">

        <section id="admin" class="tab-content active">
            <div class="grid grid-cols-12 gap-6">
                <div class="col-span-3 glass-card p-5">
                    <h3 class="border-l-4 border-red-600 pl-2 mb-4 font-bold">劳动力供给监测</h3>
                    <div class="space-y-4">
                        <div class="bg-white/5 p-3 rounded">
                            <div class="flex justify-between text-xs text-gray-400 mb-1"><span>活跃绣娘</span><span>842人</span></div>
                            <div class="h-1 bg-gray-800 rounded-full"><div class="h-full yi-red w-3/4"></div></div>
                        </div>
                        <div class="text-xs space-y-3">
                            <div class="flex items-center justify-between p-2 bg-red-900/20 border border-red-900/30 rounded">
                                <span>阿莫某某 (高级工)</span>
                                <span class="text-green-400">14:00-16:00 空闲</span>
                            </div>
                            <div class="flex items-center justify-between p-2 bg-gray-800 rounded">
                                <span>吉木某某 (中级工)</span>
                                <span class="text-gray-500">接送孩子中</span>
                            </div>
                        </div>
                        
                    </div>
                </div>
                <div class="col-span-6 glass-card p-5 relative overflow-hidden">
                    <h3 class="border-l-4 border-red-600 pl-2 mb-4 font-bold">柔性任务自动拆解与派发</h3>
                    <div class="flex items-center justify-center h-64 border-2 border-dashed border-gray-700 rounded-xl">
                        <div class="text-center">
                            <div class="animate-pulse mb-2">⚡ 正在接入市场订单: <span class="yi-yellow">棉花娃娃·彝风系列 (500件)</span></div>
                            <div class="flex space-x-2 justify-center">
                                <div class="p-2 bg-blue-600 text-[10px] rounded">工序A: 布料裁剪</div>
                                <div class="p-2 bg-red-600 text-[10px] rounded">工序B: 襟边刺绣</div>
                                <div class="p-2 bg-yellow-600 text-[10px] rounded">工序C: 饰品组装</div>
                            </div>
                            <div class="mt-4 text-xs text-gray-500">算法已匹配: 42位绣娘符合工效要求</div>
                        </div>
                    </div>
                </div>
                <div class="col-span-3 glass-card p-5">
                    <h3 class="border-l-4 border-red-600 pl-2 mb-4 font-bold">CV智能质检监控</h3>
                    <div class="aspect-square bg-black rounded mb-3 flex items-center justify-center relative border border-gray-800">
                        <div class="absolute inset-0 border-2 border-red-500 animate-pulse opacity-50"></div>
                        <span class="text-[10px] text-red-500 absolute top-2 left-2 font-mono">DETECTING: 走线不均</span>
                        <div class="text-center">
                            <div class="text-4xl">🔍</div>
                            <div class="text-[10px] mt-2 text-gray-400">正在对比标准图谱...</div>
                        </div>
                    </div>
                    <button class="w-full py-2 bg-red-600 hover:bg-red-700 text-sm rounded transition">推送纠偏教学至移动端</button>
                    
                </div>
            </div>
        </section>

        <section id="market" class="tab-content">
            <div class="max-w-6xl mx-auto">
                <div class="relative h-64 rounded-2xl overflow-hidden mb-8">
                    <img src="https://images.unsplash.com/photo-1624823183493-6f947690623a?auto=format&fit=crop&q=80&w=1200" class="w-full h-full object-cover opacity-60">
                    <div class="absolute inset-0 bg-gradient-to-t from-black to-transparent flex flex-col justify-end p-8">
                        <h2 class="text-4xl font-bold italic">非遗的现代重塑</h2>
                        <p class="yi-yellow mt-2">源自四川越西县·跨越千年的指尖温度</p>
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-8">
                    <div class="glass-card p-6 border-t-4 border-blue-500">
                        <div class="flex justify-between items-center mb-6">
                            <h3 class="text-2xl font-bold">潮流文创专区</h3>
                            <span class="text-xs bg-blue-500 px-2 py-1 rounded">标准化生产</span>
                        </div>
                        <div class="grid grid-cols-2 gap-4">
                            <div class="bg-white/5 p-2 rounded">
                                <div class="aspect-square bg-gray-800 rounded mb-2 flex items-center justify-center text-xs">娃娃服·曜石款</div>
                                <div class="flex justify-between text-sm"><span>￥49.00</span><button class="yi-yellow text-xs">加入购物车</button></div>
                            </div>
                            <div class="bg-white/5 p-2 rounded">
                                <div class="aspect-square bg-gray-800 rounded mb-2 flex items-center justify-center text-xs">刺绣钥匙扣</div>
                                <div class="flex justify-between text-sm"><span>￥19.90</span><button class="yi-yellow text-xs">加入购物车</button></div>
                            </div>
                        </div>
                    </div>
                    <div class="glass-card p-6 border-t-4 border-yellow-500">
                        <div class="flex justify-between items-center mb-6">
                            <h3 class="text-2xl font-bold">非遗高端定制</h3>
                            <span class="text-xs bg-yellow-500 px-2 py-1 rounded">匠心孤品</span>
                        </div>
                        <div class="space-y-4">
                            <div class="flex items-center space-x-4 p-3 bg-white/5 rounded">
                                <div class="w-16 h-16 bg-gray-800 rounded flex items-center justify-center text-[10px]">手工礼服</div>
                                <div class="flex-1">
                                    <div class="text-sm">彝族图腾定制·大凉山风情</div>
                                    <div class="text-xs text-gray-500 mt-1">预计工时：15个工作日</div>
                                </div>
                                <button class="px-4 py-2 yi-red text-xs rounded">发起洽谈</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="trace" class="tab-content">
            <div class="max-w-4xl mx-auto glass-card p-10">
                <div class="text-center mb-10">
                    <h2 class="text-2xl font-bold">订单流水号: <span class="yi-yellow">YX-20251225-888</span></h2>
                    <p class="text-gray-500 text-sm mt-2">该订单正在越西县城北感恩社区进行手工制作</p>
                </div>
                
                <div class="relative flex justify-between mb-16 px-10">
                    <div class="absolute top-1/2 left-0 right-0 h-1 bg-gray-800 -translate-y-1/2 z-0"></div>
                    <div class="absolute top-1/2 left-0 w-2/3 h-1 yi-red -translate-y-1/2 z-0 transition-all duration-1000"></div>
                    <div class="relative z-10 text-center">
                        <div class="w-8 h-8 yi-red rounded-full flex items-center justify-center mx-auto mb-2 text-xs">✓</div>
                        <div class="text-[10px]">任务下发</div>
                    </div>
                    <div class="relative z-10 text-center">
                        <div class="w-8 h-8 yi-red rounded-full flex items-center justify-center mx-auto mb-2 text-xs">✓</div>
                        <div class="text-[10px]">手工缝制中</div>
                    </div>
                    <div class="relative z-10 text-center">
                        <div class="w-8 h-8 bg-gray-800 rounded-full border-2 border-red-600 flex items-center justify-center mx-auto mb-2 text-xs">○</div>
                        <div class="text-[10px]">AI质检</div>
                    </div>
                    <div class="relative z-10 text-center">
                        <div class="w-8 h-8 bg-gray-800 rounded-full flex items-center justify-center mx-auto mb-2 text-xs text-gray-600">4</div>
                        <div class="text-[10px] text-gray-600">打包发货</div>
                    </div>
                </div>

                <div class="bg-black border border-red-900/50 rounded-2xl p-6 flex items-center space-x-6">
                    <div class="w-32 h-32 bg-gray-800 rounded-xl flex items-center justify-center">绣娘照片</div>
                    <div class="flex-1">
                        <h4 class="text-lg font-bold">创作者：阿莫某某</h4>
                        <div class="text-xs text-gray-400 mt-2 leading-relaxed">
                            "我是越西县安置区的居民，家里的两个孩子正在上小学。感谢您的这份订单，让我能利用下午接孩子前的空闲时间挣到一份工资。每一个针脚都带着我对未来的希望。"
                        </div>
                        <div class="mt-4 flex space-x-2">
                            <span class="px-2 py-1 bg-red-900/30 text-[10px] text-red-400">非遗二级技师</span>
                            <span class="px-2 py-1 bg-yellow-900/30 text-[10px] text-yellow-400">履约信用 99.8</span>
                        </div>
                    </div>
                    <div class="text-center">
                        <div class="text-xs text-gray-500 mb-1">扫描二维码溯源</div>
                        <div class="w-20 h-20 bg-white p-1 rounded">
                            <div class="w-full h-full bg-gray-200">QR</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <script>
        function showTab(tabId) {
            // 隐藏所有内容
            document.querySelectorAll('.tab-content').forEach(tab => tab.classList.remove('active'));
            // 移除导航栏激活状态
            document.querySelectorAll('.nav-btn').forEach(btn => btn.classList.remove('active'));
            // 显示目标内容
            document.getElementById(tabId).classList.add('active');
            // 激活对应按钮
            document.getElementById('btn-' + tabId).classList.add('active');
        }
    </script>
</body>
</html>
