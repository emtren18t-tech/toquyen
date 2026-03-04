<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EvoLab - AI Image Evolution</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap');
        
        body { 
            font-family: 'Plus Jakarta Sans', sans-serif; 
            background-color: #020617; 
            color: #f1f5f9;
            overflow-x: hidden;
        }

        .glass-panel { 
            background: rgba(15, 23, 42, 0.7); 
            backdrop-filter: blur(16px); 
            border: 1px solid rgba(51, 65, 85, 0.5); 
        }

        .loader-ring {
            border: 3px solid rgba(99, 102, 241, 0.1);
            border-top: 3px solid #6366f1;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
        }

        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }

        .custom-scrollbar::-webkit-scrollbar { width: 4px; }
        .custom-scrollbar::-webkit-scrollbar-thumb { background: #334155; border-radius: 10px; }

        .image-container {
            position: relative;
            aspect-ratio: 16 / 9;
            background: #0f172a;
            border-radius: 24px;
            overflow: hidden;
            border: 1px dashed #334155;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .image-container img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }
    </style>
</head>
<body class="min-h-screen p-4 md:p-8">

    <div class="max-w-6xl mx-auto space-y-6">
        <!-- Header -->
        <header class="glass-panel p-6 rounded-[2.5rem] flex flex-col md:flex-row justify-between items-center gap-6 shadow-2xl">
            <div class="flex items-center gap-4">
                <div class="w-14 h-14 bg-indigo-600 rounded-2xl flex items-center justify-center shadow-lg shadow-indigo-600/40">
                    <i data-lucide="sparkles" class="text-white fill-white"></i>
                </div>
                <div>
                    <h1 class="text-2xl font-black italic tracking-tighter">EVO.LAB</h1>
                    <p class="text-[10px] text-slate-500 font-mono tracking-widest uppercase">AI Evolution Web Platform</p>
                </div>
            </div>
            
            <div class="flex flex-wrap justify-center gap-3">
                <div id="shareInfo" class="hidden flex items-center gap-2">
                    <div class="bg-slate-950 px-4 py-3 rounded-2xl border border-slate-800 flex items-center gap-3">
                        <span id="displayId" class="text-xs font-mono text-indigo-400 font-bold">ID: ----</span>
                        <button onclick="copyCurrentLink()" class="text-slate-400 hover:text-white transition-colors">
                            <i data-lucide="copy" size="16"></i>
                        </button>
                    </div>
                </div>
                <button onclick="publishToCloud()" id="btnPublish" class="bg-indigo-600 hover:bg-indigo-500 px-6 py-3 rounded-2xl text-xs font-bold flex items-center gap-2 transition-all active:scale-95 shadow-lg shadow-indigo-600/20">
                    <i data-lucide="share-2" size="16"></i> XUẤT BẢN & CHIA SẺ
                </button>
            </div>
        </header>

        <main class="grid grid-cols-1 lg:grid-cols-12 gap-8">
            <!-- Left: Workspace -->
            <div class="lg:col-span-8 space-y-6">
                <!-- Main Preview -->
                <div id="uploadArea" class="image-container cursor-pointer group">
                    <div id="emptyPrompt" class="text-center p-10 transition-transform duration-500 group-hover:scale-105">
                        <div class="w-20 h-20 bg-slate-900 rounded-full flex items-center justify-center mx-auto mb-6 border border-slate-800">
                            <i data-lucide="image-plus" class="text-slate-600" size="32"></i>
                        </div>
                        <h3 class="text-lg font-bold text-slate-400">Tải ảnh gốc lên</h3>
                        <p class="text-[10px] text-slate-600 mt-2 uppercase tracking-widest">Click để chọn file từ thiết bị</p>
                    </div>
                    <img id="activeImage" class="hidden" alt="Main Content">
                    
                    <!-- Loading State -->
                    <div id="loadingOverlay" class="hidden absolute inset-0 bg-slate-950/90 backdrop-blur-xl flex flex-col items-center justify-center text-center z-50">
                        <div class="loader-ring mb-6"></div>
                        <h4 class="text-xl font-black text-white italic tracking-widest uppercase">Đang tiến hóa...</h4>
                        <p class="text-indigo-400 text-[10px] font-mono animate-pulse mt-2 tracking-[0.4em]">PROCESSING NEURAL NETWORK...</p>
                    </div>
                </div>

                <!-- Interaction Bar -->
                <div class="glass-panel p-2 rounded-[2rem] flex flex-col md:flex-row gap-2">
                    <input type="text" id="evolutionPrompt" placeholder="Nhập yêu cầu biến đổi (VD: biến thành phong cách Cyberpunk, thêm tuyết rơi)..." class="flex-1 bg-transparent px-6 py-4 outline-none text-white placeholder:text-slate-600 text-sm">
                    <button onclick="requestEvolution()" id="btnEvolve" disabled class="bg-indigo-600 hover:bg-indigo-500 disabled:opacity-30 px-10 py-4 rounded-2xl font-black text-xs text-white shadow-lg transition-all flex items-center justify-center gap-2">
                        <i data-lucide="wand-2" size="18"></i> TIẾN HÓA
                    </button>
                </div>
                <div id="errorBox" class="hidden bg-red-500/10 border border-red-500/20 p-4 rounded-2xl text-red-500 text-xs font-bold italic"></div>
            </div>

            <!-- Right: History -->
            <div class="lg:col-span-4 space-y-4">
                <div class="glass-panel p-6 rounded-[2.5rem] flex flex-col gap-6 max-h-[600px]">
                    <div class="flex items-center justify-between px-2">
                        <div class="flex items-center gap-2 text-slate-400">
                            <i data-lucide="layers" size="16"></i>
                            <span class="text-[10px] font-black uppercase tracking-widest">Lịch sử biến đổi</span>
                        </div>
                        <div id="stepCounter" class="text-[10px] font-mono text-indigo-400 bg-indigo-500/10 px-3 py-1 rounded-full">BƯỚC: 0</div>
                    </div>
                    
                    <div id="evolutionHistory" class="flex lg:flex-col gap-4 overflow-y-auto pr-2 custom-scrollbar">
                        <!-- History items -->
                    </div>

                    <button id="downloadBtn" onclick="saveImage()" class="hidden w-full py-4 bg-slate-950 border border-slate-800 hover:bg-slate-800 rounded-2xl flex items-center justify-center gap-3 text-[10px] font-black tracking-widest transition-all">
                        <i data-lucide="download" size="16"></i> TẢI ẢNH VỀ MÁY
                    </button>
                </div>
            </div>
        </main>
    </div>

    <input type="file" id="imageInput" class="hidden" accept="image/*">

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.3.1/firebase-app.js";
        import { getFirestore, doc, setDoc, getDoc } from "https://www.gstatic.com/firebasejs/11.3.1/firebase-firestore.js";
        import { getAuth, signInAnonymously } from "https://www.gstatic.com/firebasejs/11.3.1/firebase-auth.js";

        // Firebase Configuration
        const firebaseConfig = JSON.parse(__firebase_config);
        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const auth = getAuth(app);
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'evolab-shared-app';

        let history = [];
        let currentIndex = -1;
        const apiKey = ""; // API Key được hệ thống cung cấp tự động

        // Icons
        lucide.createIcons();

        // Load share data if ID exists
        window.addEventListener('load', async () => {
            await signInAnonymously(auth);
            const urlParams = new URLSearchParams(window.location.search);
            const sid = urlParams.get('share');
            if (sid) {
                setLoading(true);
                try {
                    const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'evolutions', sid);
                    const snap = await getDoc(docRef);
                    if (snap.exists()) {
                        history = snap.data().history;
                        renderUI(history.length - 1);
                        updateShareUI(sid);
                    }
                } catch (e) { console.error("Lỗi tải dữ liệu:", e); }
                setLoading(false);
            }
        });

        // Image Selection
        const uploadArea = document.getElementById('uploadArea');
        const fileInput = document.getElementById('imageInput');
        uploadArea.onclick = () => fileInput.click();
        
        fileInput.onchange = (e) => {
            const file = e.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = (ev) => {
                    history = [ev.target.result];
                    renderUI(0);
                };
                reader.readAsDataURL(file);
            }
        };

        // Evolution Request
        window.requestEvolution = async () => {
            const promptValue = document.getElementById('evolutionPrompt').value;
            if (!promptValue || currentIndex < 0) return;

            setLoading(true);
            const base64Data = history[currentIndex].split(',')[1];

            try {
                // Sử dụng Gemini Flash Image Preview để xử lý ảnh
                const response = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-image-preview:generateContent?key=${apiKey}`, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({
                        contents: [{ parts: [
                            { text: `Sửa đổi bức ảnh này theo yêu cầu: ${promptValue}. Hãy giữ nguyên khung cảnh chính và đối tượng chính nhưng thay đổi phong cách hoặc thêm chi tiết theo mô tả.` },
                            { inlineData: { mimeType: "image/png", data: base64Data } }
                        ]}],
                        generationConfig: { responseModalities: ['IMAGE'] }
                    })
                });

                const data = await response.json();
                const resultBase64 = data.candidates?.[0]?.content?.parts?.find(p => p.inlineData)?.inlineData?.data;
                
                if (resultBase64) {
                    history.push(`data:image/png;base64,${resultBase64}`);
                    renderUI(history.length - 1);
                    document.getElementById('evolutionPrompt').value = '';
                } else {
                    throw new Error("Không thể xử lý ảnh. Vui lòng thử lại yêu cầu khác.");
                }
            } catch (err) {
                const errBox = document.getElementById('errorBox');
                errBox.innerText = err.message;
                errBox.classList.remove('hidden');
                setTimeout(() => errBox.classList.add('hidden'), 5000);
            }
            setLoading(false);
        };

        // Cloud Persistence
        window.publishToCloud = async () => {
            if (history.length === 0) return;
            if (!auth.currentUser) await signInAnonymously(auth);
            
            setLoading(true);
            const sid = Math.random().toString(36).substring(2, 10);
            try {
                await setDoc(doc(db, 'artifacts', appId, 'public', 'data', 'evolutions', sid), {
                    history: history,
                    createdAt: Date.now(),
                    userId: auth.currentUser.uid
                });
                updateShareUI(sid);
                alert("Đã xuất bản thành công! Hãy copy link để chia sẻ với mọi người.");
            } catch (e) { 
                console.error(e);
                alert("Lỗi khi lưu trữ lên mây."); 
            }
            setLoading(false);
        };

        function renderUI(index) {
            currentIndex = index;
            const activeImg = document.getElementById('activeImage');
            const emptyState = document.getElementById('emptyPrompt');
            
            activeImg.src = history[index];
            activeImg.classList.remove('hidden');
            emptyState.classList.add('hidden');
            
            document.getElementById('btnEvolve').disabled = false;
            document.getElementById('downloadBtn').classList.remove('hidden');
            document.getElementById('stepCounter').innerText = `BƯỚC: ${history.length}`;

            // Update Sidebar History
            const historyList = document.getElementById('evolutionHistory');
            historyList.innerHTML = history.map((img, i) => `
                <div onclick="window.selectStep(${i})" class="relative min-w-[120px] lg:min-w-full h-24 rounded-2xl overflow-hidden border-2 cursor-pointer transition-all ${i === index ? 'border-indigo-500 scale-95 shadow-lg' : 'border-slate-800 opacity-60 hover:opacity-100'}">
                    <img src="${img}" class="w-full h-full object-cover">
                    <div class="absolute bottom-2 right-2 bg-black/60 backdrop-blur-md text-[8px] font-bold px-2 py-1 rounded text-white">#${i}</div>
                </div>
            `).reverse().join('');
        }

        function updateShareUI(sid) {
            document.getElementById('displayId').innerText = `ID: ${sid}`;
            document.getElementById('shareInfo').classList.remove('hidden');
            window.currentShareId = sid;
        }

        window.selectStep = (i) => renderUI(i);
        window.setLoading = (isLoading) => document.getElementById('loadingOverlay').classList.toggle('hidden', !isLoading);
        
        window.copyCurrentLink = () => {
            const fullUrl = `${window.location.origin}${window.location.pathname}?share=${window.currentShareId}`;
            const el = document.createElement('textarea');
            el.value = fullUrl;
            document.body.appendChild(el);
            el.select();
            document.execCommand('copy');
            document.body.removeChild(el);
            alert("Đã copy liên kết chia sẻ!");
        };

        window.saveImage = () => {
            const link = document.createElement('a');
            link.href = history[currentIndex];
            link.download = `evolab-result-${currentIndex}.png`;
            link.click();
        };
    </script>
</body>
</html>
