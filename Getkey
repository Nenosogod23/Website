```html
<!DOCTYPE html>
<html lang="th" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexus Key System - Roblox Gateway</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts: Prompt & JetBrains Mono -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;800&family=Prompt:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        cyber: {
                            dark: '#080b11',
                            card: '#121824',
                            border: '#1f293d',
                            accent: '#6366f1',
                            purple: '#a855f7',
                            cyan: '#06b6d4',
                            emerald: '#10b981',
                            amber: '#f59e0b',
                            rose: '#f43f5e'
                        }
                    },
                    fontFamily: {
                        sans: ['Prompt', 'sans-serif'],
                        mono: ['JetBrains Mono', 'monospace']
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #080b11;
            background-image: 
                radial-gradient(at 0% 0%, rgba(99, 102, 241, 0.15) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(168, 85, 247, 0.15) 0px, transparent 50%),
                radial-gradient(at 50% 50%, rgba(6, 182, 212, 0.08) 0px, transparent 60%);
            background-attachment: fixed;
        }

        .glass-panel {
            background: rgba(18, 24, 36, 0.85);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }

        .glow-indigo { box-shadow: 0 0 25px -5px rgba(99, 102, 241, 0.35); }
        .glow-emerald { box-shadow: 0 0 25px -5px rgba(16, 185, 129, 0.35); }
        .glow-amber { box-shadow: 0 0 25px -5px rgba(245, 158, 11, 0.35); }
        .glow-rose { box-shadow: 0 0 25px -5px rgba(244, 63, 94, 0.35); }

        .progress-bar-animated {
            background: linear-gradient(90deg, #6366f1, #a855f7, #06b6d4);
            background-size: 200% 100%;
            animation: gradientMove 3s ease infinite;
        }

        @keyframes gradientMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes pulseGlow {
            0%, 100% { opacity: 0.7; }
            50% { opacity: 1; filter: drop-shadow(0 0 12px rgba(168, 85, 247, 0.8)); }
        }

        .pulse-text {
            animation: pulseGlow 2.5s infinite;
        }
    </style>
</head>
<body class="font-sans text-slate-200 min-h-screen flex flex-col justify-between antialiased selection:bg-indigo-500 selection:text-white">

    <!-- Top Navigation Bar -->
    <header class="sticky top-0 z-40 glass-panel border-b border-slate-800/80">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            
            <!-- Brand Logo (Secret Admin Portal trigger on Click 3 times) -->
            <div onclick="triggerSecretAdmin()" class="flex items-center gap-3 cursor-pointer group selection:bg-none" title="คลิก 3 ครั้งติดต่อกันเพื่อเข้าหลังบ้านผ่านประตูลับ">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-indigo-600 via-purple-600 to-cyan-400 p-0.5 flex items-center justify-center shadow-lg shadow-indigo-500/20 group-hover:scale-105 transition duration-200">
                    <div class="w-full h-full bg-cyber-dark rounded-[10px] flex items-center justify-center">
                        <i class="fa-solid font-mono font-bold text-transparent bg-clip-text bg-gradient-to-r from-indigo-400 to-cyan-400 text-xl">N</i>
                    </div>
                </div>
                <div>
                    <span class="font-bold text-lg tracking-wide text-white flex items-center gap-2 group-hover:text-indigo-400 transition">
                        NEXUS <span class="text-xs px-2 py-0.5 rounded-full bg-indigo-500/20 text-indigo-400 border border-indigo-500/30 font-mono">GATEWAY</span>
                    </span>
                    <p class="text-[11px] text-slate-400 hidden sm:block">Roblox Key Verification System</p>
                </div>
            </div>

            <!-- Header Status & User Wallet -->
            <div class="flex items-center gap-3">
                <!-- User Account Info -->
                <div id="nav-user-profile" class="flex items-center gap-2 px-3 py-1.5 rounded-full bg-slate-900 border border-slate-800 text-xs">
                    <i class="fa-solid fa-user-circle text-indigo-400"></i>
                    <span id="nav-username-display" class="font-bold text-white">Guest</span>
                    <button onclick="openAuthModal()" class="ml-1 text-xs text-indigo-400 hover:underline">
                        (สลับบัญชี/เข้าสู่ระบบ)
                    </button>
                </div>

                <!-- User Wallet Balance Badge -->
                <div onclick="switchTab('wallet')" class="cursor-pointer flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-amber-500/10 border border-amber-500/30 text-amber-300 text-xs font-bold hover:bg-amber-500/20 transition shadow-sm">
                    <i class="fa-solid fa-wallet text-amber-400"></i>
                    <span>฿<span id="nav-user-balance">0.00</span></span>
                    <span class="text-[10px] bg-amber-500/30 px-1.5 py-0.2 rounded-full text-amber-200">+เติม</span>
                </div>
            </div>
        </div>
    </header>

    <!-- Global Toast Notification -->
    <div id="toast" class="fixed top-20 right-4 z-50 transform translate-x-full opacity-0 transition-all duration-300 pointer-events-none">
        <div id="toast-box" class="glass-panel border-l-4 border-indigo-500 px-4 py-3 rounded-lg shadow-2xl flex items-center gap-3 text-sm min-w-[280px]">
            <i id="toast-icon" class="fa-solid fa-circle-check text-indigo-400 text-base"></i>
            <span id="toast-message" class="text-slate-200 font-medium">ข้อความแจ้งเตือน</span>
        </div>
    </div>

    <!-- IMAGE LIGHTBOX MODAL (VIEW SLIP) -->
    <div id="image-viewer-modal" class="fixed inset-0 z-50 bg-slate-950/90 backdrop-blur-md flex items-center justify-center p-4 hidden">
        <div class="glass-panel p-4 rounded-2xl border border-indigo-500/30 max-w-lg w-full space-y-3 relative text-center">
            <button onclick="closeImageViewer()" class="absolute top-3 right-3 w-8 h-8 rounded-full bg-slate-800 text-slate-300 hover:text-white flex items-center justify-center">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <h4 class="text-sm font-bold text-white flex items-center justify-center gap-2">
                <i class="fa-solid fa-image text-indigo-400"></i> หลักฐานสลิปโอนเงิน / ภาพแนบ
            </h4>
            <div class="bg-slate-950 p-2 rounded-xl border border-slate-800 max-h-[70vh] overflow-auto">
                <img id="viewer-img" src="" alt="Slip Preview" class="w-full h-auto rounded-lg object-contain mx-auto">
            </div>
            <button onclick="closeImageViewer()" class="w-full py-2 bg-slate-800 text-slate-300 text-xs font-bold rounded-xl">
                ปิดรูปภาพ
            </button>
        </div>
    </div>

    <!-- AUTH MODAL -->
    <div id="auth-modal" class="fixed inset-0 z-50 bg-slate-950/85 backdrop-blur-md flex items-center justify-center p-4 hidden">
        <div class="glass-panel p-6 sm:p-8 rounded-2xl border border-indigo-500/40 max-w-md w-full space-y-5 glow-indigo relative">
            <button onclick="closeAuthModal()" class="absolute top-4 right-4 text-slate-400 hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <div class="text-center space-y-1">
                <div class="w-12 h-12 rounded-2xl bg-indigo-500/10 text-indigo-400 flex items-center justify-center text-xl border border-indigo-500/30 mx-auto">
                    <i class="fa-solid fa-user-shield"></i>
                </div>
                <h3 id="auth-title" class="text-xl font-bold text-white">เข้าสู่ระบบ / สมัครสมาชิก</h3>
                <p id="auth-subtitle" class="text-xs text-slate-400">กรอกชื่อผู้ใช้และรหัสผ่านเพื่อเข้าใช้งาน</p>
            </div>

            <div class="space-y-4">
                <div>
                    <label class="block text-xs font-medium text-slate-300 mb-1">ชื่อผู้ใช้งาน (Username)</label>
                    <input type="text" id="auth-username" placeholder="กรอกชื่อผู้ใช้" class="w-full px-4 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-indigo-500">
                </div>
                <div>
                    <label class="block text-xs font-medium text-slate-300 mb-1">รหัสผ่าน (Password)</label>
                    <input type="password" id="auth-password" placeholder="กรอกรหัสผ่าน" class="w-full px-4 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-indigo-500">
                </div>

                <button onclick="submitAuthAction()" class="w-full py-3 bg-indigo-600 hover:bg-indigo-500 text-white font-bold text-xs rounded-xl transition shadow-lg shadow-indigo-600/20">
                    เข้าสู่ระบบ / สมัครสมาชิก
                </button>
            </div>
        </div>
    </div>

    <!-- APPROVAL MODAL -->
    <div id="approve-payment-modal" class="fixed inset-0 z-50 bg-slate-950/85 backdrop-blur-md flex items-center justify-center p-4 hidden">
        <div class="glass-panel p-6 sm:p-8 rounded-2xl border border-emerald-500/40 max-w-md w-full space-y-4 glow-emerald relative">
            <button onclick="closeApproveModal()" class="absolute top-4 right-4 text-slate-400 hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <div class="w-12 h-12 rounded-2xl bg-emerald-500/10 text-emerald-400 flex items-center justify-center text-xl border border-emerald-500/30 mx-auto">
                <i class="fa-solid fa-hand-holding-dollar"></i>
            </div>
            <div class="text-center">
                <h3 class="text-lg font-bold text-white">อนุมัติการชำระเงิน & เพิ่มเงิน</h3>
                <p class="text-xs text-slate-400 mt-0.5">ระบุยอดเงินที่ต้องการเติมให้บัญชีนี้</p>
            </div>

            <div class="p-4 rounded-xl bg-slate-950 border border-slate-800 space-y-2 text-xs">
                <div class="flex justify-between text-slate-400">
                    <span>ผู้ขออนุมัติ:</span>
                    <span id="modal-appr-user" class="text-white font-bold font-mono">User</span>
                </div>
                <div class="flex justify-between text-slate-400">
                    <span>ช่องทาง / หลักฐาน:</span>
                    <span id="modal-appr-details" class="text-cyan-300 font-mono truncate max-w-[200px]">Detail</span>
                </div>
                <div id="modal-appr-img-preview" class="hidden pt-2">
                    <button onclick="viewSlipImage(activeApproveImgData)" class="w-full py-1.5 bg-indigo-500/20 text-indigo-300 border border-indigo-500/30 rounded-lg text-xs font-bold flex items-center justify-center gap-1.5">
                        <i class="fa-solid fa-image"></i> กดเพื่อดูรูปภาพสลิปที่ลูกค้าแนบมา
                    </button>
                </div>
            </div>

            <div>
                <label class="block text-xs font-medium text-slate-300 mb-1">จำนวนเงินที่จะเติมเข้ากระเป๋าผู้ใช้ (บาท):</label>
                <input type="number" id="modal-appr-amount" placeholder="เช่น 50" class="w-full px-4 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-sm text-center focus:outline-none focus:border-emerald-500">
            </div>

            <div class="flex gap-2 pt-2">
                <button onclick="closeApproveModal()" class="w-1/3 py-2.5 bg-slate-800 text-slate-300 text-xs rounded-xl">ยกเลิก</button>
                <button onclick="confirmPaymentApproval()" class="w-2/3 py-2.5 bg-emerald-600 hover:bg-emerald-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-emerald-600/20">
                    ✅ ยืนยันอนุมัติเติมเงิน
                </button>
            </div>
        </div>
    </div>

    <!-- SUCCESS MODAL -->
    <div id="success-modal" class="fixed inset-0 z-50 bg-slate-950/80 backdrop-blur-md flex items-center justify-center p-4 hidden">
        <div class="glass-panel p-6 sm:p-8 rounded-2xl border border-emerald-500/30 max-w-md w-full space-y-4 glow-emerald text-center relative">
            <button onclick="closeSuccessModal()" class="absolute top-4 right-4 text-slate-400 hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            
            <div class="w-14 h-14 rounded-2xl bg-emerald-500/10 text-emerald-400 flex items-center justify-center text-2xl border border-emerald-500/30 mx-auto">
                <i class="fa-solid fa-circle-check"></i>
            </div>
            
            <div>
                <h3 id="modal-success-title" class="text-xl font-bold text-white">ทำรายการสำเร็จ!</h3>
                <p id="modal-success-desc" class="text-xs text-slate-400 mt-1">นี่คือรหัสคีย์ของคุณ สามารถคัดลอกไปใช้งานได้ทันที</p>
            </div>

            <div class="p-4 rounded-xl bg-slate-950 border border-slate-800 space-y-2">
                <input type="text" id="modal-key-display" readonly value="NEXUS-KEY-XXXXX" class="w-full bg-transparent text-center text-emerald-400 font-mono font-bold text-lg focus:outline-none">
                <button onclick="copyToClipboard(document.getElementById('modal-key-display').value, 'คัดลอกรหัสคีย์สำเร็จ!')" class="w-full py-2 bg-emerald-600 hover:bg-emerald-500 text-white rounded-lg text-xs font-semibold flex items-center justify-center gap-1.5">
                    <i class="fa-solid fa-copy"></i>
                    <span>คัดลอกรหัสคีย์</span>
                </button>
            </div>

            <button onclick="closeSuccessModal()" class="w-full py-2.5 bg-slate-800 hover:bg-slate-700 text-slate-300 font-bold text-xs rounded-xl">
                ปิดหน้าต่าง
            </button>
        </div>
    </div>

    <!-- SECRET ADMIN PIN MODAL -->
    <div id="admin-modal" class="fixed inset-0 z-50 bg-slate-950/80 backdrop-blur-md flex items-center justify-center p-4 hidden">
        <div class="glass-panel p-6 sm:p-8 rounded-2xl border border-rose-500/30 max-w-md w-full space-y-4 glow-rose text-center relative">
            <button onclick="closeAdminModal()" class="absolute top-4 right-4 text-slate-400 hover:text-white">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <div class="w-12 h-12 rounded-2xl bg-rose-500/10 text-rose-400 flex items-center justify-center text-xl border border-rose-500/20 mx-auto">
                <i class="fa-solid fa-user-lock"></i>
            </div>
            <div>
                <h3 class="text-lg font-bold text-white">ประตูลับเข้าสู่ระบบหลังบ้าน (Admin)</h3>
                <p class="text-xs text-slate-400 mt-1">กรอก PIN เพื่อเข้าสู่แผงควบคุมหลัก (PIN เริ่มต้น: <span class="text-rose-400 font-mono font-bold">1234</span>)</p>
            </div>
            <input type="password" id="modal-pin-input" placeholder="กรอกรหัส PIN" class="w-full px-4 py-3 rounded-xl bg-slate-950 border border-slate-800 text-center text-white font-mono text-sm focus:outline-none focus:border-rose-500">
            <button onclick="submitModalAdminPin()" class="w-full py-3 bg-rose-600 hover:bg-rose-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-rose-600/20">
                เข้าสู่แผงควบคุมหลังบ้าน
            </button>
        </div>
    </div>

    <!-- Main Container -->
    <main class="max-w-4xl mx-auto px-4 py-8 sm:py-12 w-full flex-grow">
        
        <!-- Hero Header -->
        <div class="text-center mb-8">
            <h1 class="text-3xl sm:text-4xl font-extrabold text-white tracking-tight mb-2">
                รับคีย์เข้าใช้งาน <span class="text-transparent bg-clip-text bg-gradient-to-r from-indigo-400 via-purple-400 to-cyan-400 pulse-text">Roblox Script</span>
            </h1>
            <p class="text-slate-400 text-sm sm:text-base max-w-xl mx-auto">
                ระบบออกรหัสคีย์อัตโนมัติ สำหรับสคริปต์ Roblox ปลอดภัย เชื่อถือได้ 100%
            </p>
        </div>

        <!-- Navigation Tabs -->
        <div class="flex justify-center mb-8">
            <div class="bg-slate-900/90 p-1.5 rounded-2xl border border-slate-800 flex flex-wrap sm:flex-nowrap gap-1.5 w-full max-w-3xl">
                <button id="tab-getkey-btn" onclick="switchTab('getkey')" class="flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 bg-indigo-600 text-white shadow-lg shadow-indigo-600/30">
                    <i class="fa-solid fa-key"></i>
                    <span>🔑 รับคีย์ฟรี</span>
                </button>
                <button id="tab-vip-btn" onclick="switchTab('vip')" class="flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 text-amber-400 hover:text-amber-300 hover:bg-slate-800/60">
                    <i class="fa-solid fa-crown text-amber-400"></i>
                    <span>👑 ซื้อคีย์ VIP</span>
                </button>
                <button id="tab-wallet-btn" onclick="switchTab('wallet')" class="flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 text-emerald-400 hover:text-emerald-300 hover:bg-slate-800/60">
                    <i class="fa-solid fa-wallet text-emerald-400"></i>
                    <span>💰 กระเป๋าเงิน</span>
                </button>
                <button id="tab-history-btn" onclick="switchTab('history')" class="flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 text-purple-400 hover:text-purple-300 hover:bg-slate-800/60">
                    <i class="fa-solid fa-clock-rotate-left text-purple-400"></i>
                    <span>📜 ประวัติ</span>
                </button>
                <!-- Dynamic Secret Admin Navbar Tab -->
                <button id="tab-admin-btn" onclick="switchTab('admin')" class="hidden flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 text-rose-400 border border-rose-500/30 bg-rose-500/10 hover:bg-rose-500/20">
                    <i class="fa-solid fa-user-gear text-rose-400"></i>
                    <span>🛠️ หลังบ้าน</span>
                </button>
            </div>
        </div>

        <!-- VIEW 1: GET FREE KEY PROCESS -->
        <div id="view-getkey" class="space-y-6">
            
            <!-- Lock Card when Key already Active -->
            <div id="active-key-lock-box" class="glass-panel p-6 rounded-2xl border border-emerald-500/40 glow-emerald hidden space-y-4">
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-xl bg-emerald-500/20 text-emerald-400 flex items-center justify-center text-lg">
                        <i class="fa-solid fa-circle-check"></i>
                    </div>
                    <div>
                        <h3 class="font-bold text-white text-base">คุณมีคีย์ฟรีที่ยังใช้งานได้อยู่!</h3>
                        <p class="text-xs text-slate-400">ไม่ต้องทำโฆษณาซ้ำ สามารถใช้งานคีย์เดิมได้จนกว่าจะหมดอายุ</p>
                    </div>
                </div>
                <div class="p-3 bg-slate-950 rounded-xl border border-slate-800 flex items-center justify-between gap-2">
                    <input type="text" id="locked-active-key" readonly value="" class="bg-transparent text-emerald-400 font-mono font-bold text-sm w-full focus:outline-none">
                    <button onclick="copyToClipboard(document.getElementById('locked-active-key').value, 'คัดลอกคีย์เรียบร้อยแล้ว!')" class="px-3 py-1.5 bg-emerald-600 hover:bg-emerald-500 text-white rounded-lg text-xs font-bold shrink-0">
                        คัดลอกคีย์
                    </button>
                </div>
                <div class="flex justify-between text-xs text-slate-400 font-mono pt-1">
                    <span>ผูกกับ HWID: <span id="locked-key-hwid" class="text-cyan-400">NEXUS-XXXX</span></span>
                    <span>หมดอายุในอีก: <span id="locked-key-expire" class="text-amber-400">--</span></span>
                </div>
            </div>

            <div id="free-key-stepper-container" class="space-y-6">
                <!-- STEP 1: Select Duration & HWID -->
                <div id="step-1" class="glass-panel p-6 sm:p-8 rounded-2xl border border-slate-800 space-y-6">
                    <div class="space-y-2">
                        <h2 class="text-xl font-bold text-white flex items-center gap-2">
                            <i class="fa-solid fa-clock text-indigo-400"></i>
                            <span>เลือกระยะเวลาคีย์ฟรี</span>
                        </h2>
                        <p class="text-xs text-slate-400">เลือกระยะเวลาที่ต้องการใช้งาน ยิ่งเลือกเวลาเยอะ จะเพิ่มจำนวน Checkpoints ในการผ่าน</p>
                    </div>

                    <!-- Duration Grid Selector -->
                    <div class="grid grid-cols-2 sm:grid-cols-4 gap-3">
                        <div onclick="selectDuration(1, 1)" id="dur-1" class="p-4 rounded-xl border border-slate-800 bg-slate-900/60 hover:border-indigo-500/50 cursor-pointer transition text-center space-y-1">
                            <span class="block font-bold text-white text-base">1 ชั่วโมง</span>
                            <span class="block text-[11px] text-slate-400">1 Checkpoint</span>
                        </div>
                        <div onclick="selectDuration(4, 2)" id="dur-4" class="p-4 rounded-xl border border-slate-800 bg-slate-900/60 hover:border-indigo-500/50 cursor-pointer transition text-center space-y-1">
                            <span class="block font-bold text-white text-base">4 ชั่วโมง</span>
                            <span class="block text-[11px] text-slate-400">2 Checkpoints</span>
                        </div>
                        <div onclick="selectDuration(12, 3)" id="dur-12" class="p-4 rounded-xl border border-slate-800 bg-slate-900/60 hover:border-indigo-500/50 cursor-pointer transition text-center space-y-1">
                            <span class="block font-bold text-white text-base">12 ชั่วโมง</span>
                            <span class="block text-[11px] text-slate-400">3 Checkpoints</span>
                        </div>
                        <div onclick="selectDuration(24, 4)" id="dur-24" class="p-4 rounded-xl border border-indigo-500 bg-indigo-500/10 cursor-pointer transition text-center space-y-1 glow-indigo">
                            <span class="block font-bold text-indigo-300 text-base">24 ชั่วโมง</span>
                            <span class="block text-[11px] text-indigo-400 font-medium">4 Checkpoints</span>
                        </div>
                    </div>

                    <!-- HWID Input -->
                    <div class="space-y-2 pt-2">
                        <label class="block text-xs font-medium text-slate-300 flex items-center justify-between">
                            <span>Roblox HWID / Key Identifier</span>
                            <span class="text-indigo-400 text-[11px]">ผูกกับบัญชีสมาชิกของคุณอัตโนมัติ</span>
                        </label>
                        <div class="relative">
                            <input type="text" id="hwid-input" readonly placeholder="ระบบจะสร้าง HWID ให้อัตโนมัติ" class="w-full px-4 py-3 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-sm focus:outline-none pr-24">
                            <button onclick="document.getElementById('hwid-input').value = generateRandomHWID()" class="absolute right-2 top-2 px-3 py-1.5 bg-slate-800 hover:bg-slate-700 text-slate-300 text-xs font-semibold rounded-lg transition">
                                สุ่ม HWID
                            </button>
                        </div>
                    </div>

                    <button onclick="goToStep2()" class="w-full py-3.5 bg-indigo-600 hover:bg-indigo-500 text-white font-bold text-sm rounded-xl transition flex items-center justify-center gap-2 shadow-lg shadow-indigo-600/25">
                        <span>เริ่มกระบวนการรับคีย์ฟรี</span>
                        <i class="fa-solid fa-arrow-right"></i>
                    </button>
                </div>

                <!-- STEP 2: Ad Checkpoints -->
                <div id="step-2" class="glass-panel p-6 sm:p-8 rounded-2xl border border-slate-800 space-y-6 hidden">
                    <div class="flex items-center justify-between">
                        <div>
                            <h2 class="text-xl font-bold text-white">ทำรายการ Checkpoint โฆษณา</h2>
                            <p class="text-xs text-slate-400 mt-0.5">กดปุ่มตามลำดับเพื่อปลดล็อกคีย์ใช้งาน (<span id="checkpoint-progress-text">0/4</span>)</p>
                        </div>
                        <button onclick="goToStep1()" class="text-xs text-slate-400 hover:text-white">
                            <i class="fa-solid fa-rotate-left mr-1"></i> ย้อนกลับ
                        </button>
                    </div>

                    <div id="checkpoints-list" class="space-y-3">
                        <!-- Checkpoint Items -->
                    </div>

                    <button id="get-key-final-btn" disabled onclick="generateFinalFreeKey()" class="w-full py-3.5 bg-slate-800 text-slate-500 font-bold text-sm rounded-xl transition flex items-center justify-center gap-2 cursor-not-allowed">
                        <i class="fa-solid fa-lock"></i>
                        <span>รับรหัสคีย์ (ทำโฆษณาให้ครบก่อน)</span>
                    </button>
                </div>
            </div>
        </div>

        <!-- VIEW 2: VIP KEY STORE -->
        <div id="view-vip" class="space-y-6 hidden">
            <div class="glass-panel p-6 sm:p-8 rounded-2xl border border-amber-500/30 glow-amber space-y-6">
                <div class="text-center space-y-2">
                    <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-amber-500/10 border border-amber-500/20 text-amber-400 text-xs font-bold">
                        <i class="fa-solid fa-crown"></i> NEXUS VIP PREMIUM
                    </div>
                    <h2 class="text-2xl font-bold text-white">สั่งซื้อคีย์ VIP แบบข้ามโฆษณา</h2>
                    <p class="text-slate-400 text-xs">ไม่ต้องทำ Checkpoint โฆษณา ไม่ต้องรอเวลารับคีย์</p>
                </div>

                <!-- VIP Plans -->
                <div class="grid sm:grid-cols-2 gap-4">
                    <div onclick="selectVipPlan('7d', 50)" id="plan-7d" class="p-5 rounded-xl border border-amber-500 bg-amber-500/10 cursor-pointer transition relative space-y-3 glow-amber">
                        <div class="flex justify-between items-start">
                            <div>
                                <h3 class="font-bold text-white text-lg">VIP 7 วัน</h3>
                                <p class="text-xs text-amber-300/80">ใช้งานสคริปต์ได้ต่อเนื่อง 7 วันเต็ม</p>
                            </div>
                            <span class="text-2xl font-black text-amber-400 font-mono">฿50</span>
                        </div>
                    </div>

                    <div onclick="selectVipPlan('life', 150)" id="plan-life" class="p-5 rounded-xl border border-slate-800 bg-slate-900/60 cursor-pointer hover:border-amber-500/40 transition relative space-y-3">
                        <div class="flex justify-between items-start">
                            <div>
                                <h3 class="font-bold text-white text-lg">VIP ถาวร (Lifetime)</h3>
                                <p class="text-xs text-slate-400">ใช้งานได้ตลอดชีพ ไม่มีวันหมดอายุ</p>
                            </div>
                            <span class="text-2xl font-black text-white font-mono">฿150</span>
                        </div>
                    </div>
                </div>

                <!-- Payment Options -->
                <div class="space-y-3 pt-2">
                    <div class="grid grid-cols-3 gap-2">
                        <div onclick="setPayMethod('wallet')" id="pay-opt-wallet" class="p-3 rounded-xl border border-emerald-500 bg-emerald-500/10 cursor-pointer text-white font-bold text-xs flex flex-col items-center justify-center gap-1 text-center">
                            <i class="fa-solid fa-wallet text-emerald-400 text-sm"></i>
                            <span>กระเป๋าเงิน (฿<span id="pay-opt-balance">0.00</span>)</span>
                        </div>
                        <div onclick="setPayMethod('truemoney')" id="pay-opt-truemoney" class="p-3 rounded-xl border border-slate-800 bg-slate-900/60 cursor-pointer text-slate-400 font-bold text-xs flex flex-col items-center justify-center gap-1 text-center hover:border-orange-500/40">
                            <i class="fa-solid fa-gift text-orange-400 text-sm"></i>
                            <span>TrueMoney (อั่งเปา)</span>
                        </div>
                        <div onclick="setPayMethod('kbank')" id="pay-opt-kbank" class="p-3 rounded-xl border border-slate-800 bg-slate-900/60 cursor-pointer text-slate-400 font-bold text-xs flex flex-col items-center justify-center gap-1 text-center hover:border-emerald-500/40">
                            <i class="fa-solid fa-building-columns text-emerald-400 text-sm"></i>
                            <span>โอน KBANK</span>
                        </div>
                    </div>
                </div>

                <!-- Pay Box Wallet -->
                <div id="pay-box-wallet" class="p-4 rounded-xl bg-slate-950 border border-slate-800 space-y-3">
                    <button onclick="buyVipWithWallet()" class="w-full py-3 bg-emerald-600 hover:bg-emerald-500 text-white font-bold text-xs rounded-xl transition shadow-lg shadow-emerald-600/20">
                        ชำระเงินด้วย Wallet Balance ทันที (฿<span id="checkout-price">50.00</span>)
                    </button>
                </div>

                <!-- Pay Box TrueMoney Angpao -->
                <div id="pay-box-truemoney" class="p-4 rounded-xl bg-slate-950 border border-slate-800 space-y-3 hidden">
                    <div class="p-3 rounded-lg bg-orange-500/10 border border-orange-500/20 text-xs text-orange-300 space-y-1">
                        <p class="font-bold"><i class="fa-solid fa-gift"></i> ชำระผ่านซองอั่งเปา TrueMoney Wallet:</p>
                        <p class="text-[11px] text-slate-400">สร้างซองอั่งเปาตามราคาสินค้า คัดลอกลิงก์ หรือแนบแคปหน้าจอรูปภาพสลิป</p>
                    </div>
                    <div>
                        <label class="block text-xs font-medium text-slate-300 mb-1">ลิงก์ซองอั่งเปา TrueMoney:</label>
                        <input type="text" id="truemoney-link-input" placeholder="https://gift.truemoney.com/campaign/?v=XXXXX" class="w-full px-4 py-2.5 rounded-xl bg-slate-900 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-orange-500">
                    </div>
                    <div>
                        <label class="block text-xs font-medium text-slate-300 mb-1">หรือ อัปโหลดรูปภาพสลิป/หลักฐาน (Optional):</label>
                        <input type="file" id="truemoney-file-input" accept="image/*" class="w-full text-xs text-slate-400 file:mr-3 file:py-2 file:px-4 file:rounded-xl file:border-0 file:text-xs file:font-semibold file:bg-orange-500/20 file:text-orange-300 hover:file:bg-orange-500/30 cursor-pointer">
                    </div>
                    <button onclick="submitTrueMoneyPayment()" class="w-full py-3 bg-orange-600 hover:bg-orange-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-orange-600/20">
                        ส่งลิงก์/สลิปแจ้งชำระเงิน VIP
                    </button>
                </div>

                <!-- Pay Box KBANK Bank Transfer -->
                <div id="pay-box-kbank" class="p-4 rounded-xl bg-slate-950 border border-slate-800 space-y-3 hidden">
                    <div class="p-3 rounded-lg bg-emerald-500/10 border border-emerald-500/20 text-xs text-emerald-300 space-y-1">
                        <p class="font-bold"><i class="fa-solid fa-building-columns"></i> ธนาคารกสิกรไทย (KBANK):</p>
                        <div class="flex items-center justify-between font-mono font-bold text-white bg-slate-900 p-2 rounded border border-slate-800">
                            <span>2123551047 (Nexus Gateway)</span>
                            <button onclick="copyToClipboard('2123551047', 'คัดลอกเลขบัญชี 2123551047 แล้ว!')" class="text-xs text-indigo-400 hover:underline">คัดลอก</button>
                        </div>
                    </div>
                    <div>
                        <label class="block text-xs font-medium text-slate-300 mb-1">หมายเลขอ้างอิงสลิป / ข้อความ:</label>
                        <input type="text" id="kbank-slip-input" placeholder="กรอกเลขสลิป หรือข้อความอ้างอิง" class="w-full px-4 py-2.5 rounded-xl bg-slate-900 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-emerald-500">
                    </div>
                    <div>
                        <label class="block text-xs font-medium text-slate-300 mb-1">อัปโหลดรูปภาพสลิปโอนเงิน (Image Upload):</label>
                        <input type="file" id="kbank-file-input" accept="image/*" class="w-full text-xs text-slate-400 file:mr-3 file:py-2 file:px-4 file:rounded-xl file:border-0 file:text-xs file:font-semibold file:bg-emerald-500/20 file:text-emerald-300 hover:file:bg-emerald-500/30 cursor-pointer">
                    </div>
                    <button onclick="submitKbankPayment()" class="w-full py-3 bg-emerald-600 hover:bg-emerald-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-emerald-600/20">
                        ส่งรูปสลิปโอนเงิน KBANK เข้าหลังบ้าน
                    </button>
                </div>
            </div>
        </div>

        <!-- VIEW 3: USER WALLET & TOPUP -->
        <div id="view-wallet" class="space-y-6 hidden">
            <div class="glass-panel p-6 sm:p-8 rounded-2xl border border-emerald-500/30 glow-emerald space-y-6">
                <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4 bg-slate-950 p-5 rounded-2xl border border-slate-800">
                    <div class="flex items-center gap-3">
                        <div class="w-12 h-12 rounded-2xl bg-emerald-500/10 text-emerald-400 flex items-center justify-center text-xl border border-emerald-500/30">
                            <i class="fa-solid fa-wallet"></i>
                        </div>
                        <div>
                            <span class="text-xs text-slate-400 font-medium">ยอดเงินคงเหลือในกระเป๋า</span>
                            <h2 class="text-3xl font-black text-emerald-400 font-mono">฿<span id="wallet-balance-big">0.00</span></h2>
                        </div>
                    </div>
                </div>

                <!-- Topup Channel Tabs -->
                <div class="space-y-3">
                    <h3 class="text-sm font-bold text-white">เติมเงินเข้ากระเป๋าเงิน (Wallet Topup)</h3>
                    
                    <div class="flex gap-2 mb-3">
                        <button onclick="setTopupMethod('truemoney')" id="topup-tab-true" class="flex-1 py-2 rounded-xl text-xs font-bold border border-orange-500 bg-orange-500/10 text-orange-300">
                            <i class="fa-solid fa-gift mr-1"></i> TrueMoney อั่งเปา
                        </button>
                        <button onclick="setTopupMethod('kbank')" id="topup-tab-kbank" class="flex-1 py-2 rounded-xl text-xs font-bold border border-slate-800 bg-slate-900 text-slate-400 hover:text-emerald-300">
                            <i class="fa-solid fa-building-columns mr-1"></i> โอน KBANK + สลิป
                        </button>
                    </div>

                    <div id="topup-form-true" class="space-y-3">
                        <input type="text" id="topup-true-input" placeholder="วางลิงก์ซองอั่งเปา TrueMoney Wallet" class="w-full px-4 py-3 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-orange-500">
                        <div class="flex items-center gap-2">
                            <span class="text-xs text-slate-400">หรือแนบภาพสลิป:</span>
                            <input type="file" id="topup-true-file" accept="image/*" class="text-xs text-slate-400 file:mr-2 file:py-1 file:px-3 file:rounded-lg file:border-0 file:text-xs file:bg-slate-800 file:text-slate-300">
                        </div>
                        <button onclick="submitWalletTopupTrue()" class="w-full py-3 bg-orange-600 hover:bg-orange-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-orange-600/20">
                            ส่งซองอั่งเปา/สลิปเติมเงิน (รออนุมัติ)
                        </button>
                    </div>

                    <div id="topup-form-kbank" class="space-y-3 hidden">
                        <div class="p-3 rounded-lg bg-emerald-500/10 border border-emerald-500/20 text-xs text-emerald-300 flex items-center justify-between font-mono">
                            <span>KBANK: 2123551047 (Nexus Gateway)</span>
                            <button onclick="copyToClipboard('2123551047', 'คัดลอกเลขบัญชี 2123551047!')" class="text-xs text-indigo-400 hover:underline">คัดลอก</button>
                        </div>
                        <input type="text" id="topup-kbank-input" placeholder="กรอกหมายเลขอ้างอิงสลิป (ถ้ามี)" class="w-full px-4 py-3 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-emerald-500">
                        <div>
                            <label class="block text-xs font-medium text-slate-300 mb-1">อัปโหลดรูปภาพสลิปโอนเงิน (Image Upload):</label>
                            <input type="file" id="topup-kbank-file" accept="image/*" class="w-full text-xs text-slate-400 file:mr-3 file:py-2 file:px-4 file:rounded-xl file:border-0 file:text-xs file:font-semibold file:bg-emerald-500/20 file:text-emerald-300 hover:file:bg-emerald-500/30 cursor-pointer">
                        </div>
                        <button onclick="submitWalletTopupKbank()" class="w-full py-3 bg-emerald-600 hover:bg-emerald-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-emerald-600/20">
                            ส่งรูปสลิป KBANK เติมเงิน (รออนุมัติ)
                        </button>
                    </div>
                </div>

                <div class="pt-4 border-t border-slate-800 space-y-3">
                    <h3 class="text-sm font-bold text-white">กรอกโค้ดรับเงินฟรี / โค้ดโปรโมชัน</h3>
                    <div class="flex gap-2">
                        <input type="text" id="redeem-code-input" placeholder="เช่น FREE50" class="w-full px-4 py-2.5 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-xs uppercase focus:outline-none focus:border-amber-500">
                        <button onclick="redeemBalanceCode()" class="px-5 py-2.5 bg-amber-600 hover:bg-amber-500 text-white font-bold text-xs rounded-xl shrink-0">
                            เติมโค้ด
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <!-- VIEW 4: HISTORY -->
        <div id="view-history" class="space-y-6 hidden">
            <div class="glass-panel p-6 sm:p-8 rounded-2xl border border-slate-800 space-y-4">
                <h2 class="text-xl font-bold text-white flex items-center gap-2">
                    <i class="fa-solid fa-clock-rotate-left text-purple-400"></i>
                    <span>ประวัติคีย์ของคุณ</span>
                </h2>
                <div id="user-history-list" class="space-y-3">
                    <!-- History Rendered Here -->
                </div>
            </div>
        </div>

        <!-- VIEW 5: ADMIN BACK-OFFICE PANEL -->
        <div id="view-admin" class="space-y-6 hidden">
            <div class="glass-panel p-6 sm:p-8 rounded-2xl border border-rose-500/40 glow-rose space-y-6">
                <div class="flex justify-between items-center border-b border-slate-800 pb-4">
                    <div>
                        <h2 class="text-xl font-bold text-white text-rose-400 flex items-center gap-2">
                            <i class="fa-solid fa-user-gear"></i> แผงควบคุมหลังบ้าน (Admin Management)
                        </h2>
                        <p class="text-xs text-slate-400">จัดการสลิป/ซองอั่งเปา, คีย์ฟรี-VIP และโค้ดส่วนลดโปรโมชัน</p>
                    </div>
                    <button onclick="lockAdmin()" class="px-3 py-1.5 bg-rose-500/20 text-rose-300 border border-rose-500/30 rounded-lg text-xs font-bold hover:bg-rose-500/30 transition">
                        🔒 ออกจากระบบหลังบ้าน
                    </button>
                </div>

                <!-- Admin Section 1: Pending Payments -->
                <div class="space-y-3">
                    <h3 class="text-sm font-bold text-white flex items-center justify-between">
                        <span>📋 รายการแจ้งชำระเงิน VIP / อั่งเปา (รออนุมัติ)</span>
                        <span id="pending-count-badge" class="px-2 py-0.5 rounded-full bg-amber-500/20 text-amber-300 text-xs font-mono">0</span>
                    </h3>
                    <div id="admin-pending-payments-list" class="space-y-3">
                        <!-- Pending Payments Rendered Here -->
                    </div>
                </div>

                <!-- Admin Section 2: Key Management (🔑 เสกคีย์ VIP/ฟรี & จัดการลบคีย์) -->
                <div class="pt-4 border-t border-slate-800 space-y-4">
                    <h3 class="text-sm font-bold text-white flex items-center justify-between">
                        <span>🔑 สร้าง & จัดการคีย์ในระบบ (Key Manager)</span>
                        <span id="keys-count-badge" class="px-2 py-0.5 rounded-full bg-indigo-500/20 text-indigo-300 text-xs font-mono">0</span>
                    </h3>
                    
                    <!-- Create Custom Key Form -->
                    <div class="p-4 rounded-xl bg-slate-950 border border-slate-800 space-y-3">
                        <span class="text-xs font-bold text-indigo-400 block">➕ ออกคีย์ใหม่ให้ผู้ใช้โดยตรง (Manual Key Generator)</span>
                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                            <input type="text" id="adm-key-user" placeholder="ชื่อบัญชีผู้ใช้ (Username)" class="px-3 py-2 rounded-xl bg-slate-900 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-indigo-500">
                            <select id="adm-key-type" class="px-3 py-2 rounded-xl bg-slate-900 border border-slate-800 text-white text-xs focus:outline-none focus:border-indigo-500">
                                <option value="FREE-24H">ฟรี (24 ชั่วโมง)</option>
                                <option value="VIP-7D">👑 VIP (7 วัน)</option>
                                <option value="VIP-LIFETIME">👑 VIP (ถาวร/Lifetime)</option>
                            </select>
                            <input type="text" id="adm-key-hwid" placeholder="HWID (ถ้าไม่ใส่จะสุ่มให้)" class="px-3 py-2 rounded-xl bg-slate-900 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-indigo-500">
                        </div>
                        <button onclick="adminCreateCustomKey()" class="w-full py-2.5 bg-indigo-600 hover:bg-indigo-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-indigo-600/20 transition">
                            ออกคีย์ใหม่และบันทึกเข้าฐานข้อมูล
                        </button>
                    </div>

                    <!-- Keys List -->
                    <div id="admin-keys-list" class="space-y-2 pt-2 max-h-60 overflow-y-auto">
                        <!-- Keys Rendered Here -->
                    </div>
                </div>

                <!-- Admin Section 3: Coupon Creator & List (🎟️ สร้าง & ลบโค้ด) -->
                <div class="pt-4 border-t border-slate-800 space-y-4">
                    <h3 class="text-sm font-bold text-white flex items-center justify-between">
                        <span>🎟️ สร้างและจัดการโค้ดเงินฟรี / ส่วนลด (Coupons)</span>
                        <span id="coupons-count-badge" class="px-2 py-0.5 rounded-full bg-amber-500/20 text-amber-300 text-xs font-mono">0</span>
                    </h3>
                    
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                        <input type="text" id="adm-coupon-code" placeholder="ชื่อโค้ด (เช่น FREE50)" class="px-3 py-2 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-xs uppercase focus:outline-none focus:border-amber-500">
                        <input type="number" id="adm-coupon-val" placeholder="มูลค่าเงิน (บาท)" class="px-3 py-2 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-amber-500">
                        <input type="number" id="adm-coupon-max" placeholder="จำนวนสิทธิ์ใช้งานสูงสุด" class="px-3 py-2 rounded-xl bg-slate-950 border border-slate-800 text-white font-mono text-xs focus:outline-none focus:border-amber-500">
                    </div>
                    <button onclick="createNewCoupon()" class="w-full py-2.5 bg-amber-600 hover:bg-amber-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-amber-600/20 transition">
                        สร้างโค้ดโปรโมชันใหม่
                    </button>

                    <div id="admin-coupons-list" class="space-y-2 pt-2 max-h-60 overflow-y-auto">
                        <!-- Coupons Rendered Here -->
                    </div>
                </div>
            </div>
        </div>

    </main>

    <footer class="py-6 border-t border-slate-900 text-center text-slate-500 text-xs">
        <p>© 2026 Nexus Key Gateway System. All rights reserved.</p>
    </footer>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        // Storage Keys
        const STORAGE_KEYS = {
            USERS: 'NEXUS_USERS_V2',
            CURRENT_USER: 'NEXUS_CURR_USER_V2',
            KEYS: 'NEXUS_KEYS_V2',
            PAYMENTS: 'NEXUS_PAYMENTS_V2',
            COUPONS: 'NEXUS_COUPONS_V2',
            ADMIN_PIN: 'NEXUS_ADMIN_PIN_V2'
        };

        // State Variables
        let secretClickCount = 0;
        let secretClickTimer = null;
        let isAdminUnlocked = false;
        let activeApproveId = null;
        let activeApproveImgData = null;

        let selectedDuration = 24;
        let requiredCheckpoints = 4;
        let completedCheckpoints = 0;
        let boundHwid = '';
        let activeVipPlan = '7d';
        let activePayMethod = 'wallet';

        // Helper to read file input as Base64 image
        function readFileAsBase64(fileInput) {
            return new Promise((resolve) => {
                if (!fileInput || !fileInput.files || !fileInput.files[0]) {
                    resolve(null);
                    return;
                }
                const file = fileInput.files[0];
                const reader = new FileReader();
                reader.onload = (e) => resolve(e.target.result);
                reader.onerror = () => resolve(null);
                reader.readAsDataURL(file);
            });
        }

        function viewSlipImage(imageData) {
            if (!imageData) return;
            document.getElementById('viewer-img').src = imageData;
            document.getElementById('image-viewer-modal').classList.remove('hidden');
        }

        function closeImageViewer() {
            document.getElementById('image-viewer-modal').classList.add('hidden');
            document.getElementById('viewer-img').src = '';
        }

        // Init App
        window.onload = function() {
            initStorage();
            isAdminUnlocked = false;
            updateUserUI();
            checkActiveFreeKey();
            switchTab('getkey');
        };

        function initStorage() {
            if (!localStorage.getItem(STORAGE_KEYS.ADMIN_PIN)) {
                localStorage.setItem(STORAGE_KEYS.ADMIN_PIN, '1234');
            }
            if (!localStorage.getItem(STORAGE_KEYS.CURRENT_USER)) {
                const guestUser = 'Guest_' + Math.floor(Math.random() * 8999 + 1000);
                const guestObj = { username: guestUser, balance: 0.00, hwid: generateRandomHWID() };
                localStorage.setItem(STORAGE_KEYS.CURRENT_USER, JSON.stringify(guestObj));
            }
            if (!localStorage.getItem(STORAGE_KEYS.COUPONS)) {
                const defaultCoupons = [
                    { code: 'FREE50', val: 50, maxUsers: 50, claimedUsers: [] }
                ];
                localStorage.setItem(STORAGE_KEYS.COUPONS, JSON.stringify(defaultCoupons));
            }
        }

        function generateRandomHWID() {
            return 'NEXUS-' + Math.random().toString(36).substring(2, 6).toUpperCase() + '-' + Math.random().toString(36).substring(2, 6).toUpperCase();
        }

        function getCurrentUserData() {
            try { return JSON.parse(localStorage.getItem(STORAGE_KEYS.CURRENT_USER)); } catch(e) { return null; }
        }

        function updateCurrentUserData(updaterFn) {
            let user = getCurrentUserData();
            if (user) {
                updaterFn(user);
                localStorage.setItem(STORAGE_KEYS.CURRENT_USER, JSON.stringify(user));
                updateUserUI();
            }
        }

        function updateUserUI() {
            const user = getCurrentUserData();
            if (user) {
                document.getElementById('nav-username-display').innerText = user.username;
                document.getElementById('nav-user-balance').innerText = (user.balance || 0).toFixed(2);
                document.getElementById('wallet-balance-big').innerText = (user.balance || 0).toFixed(2);
                document.getElementById('pay-opt-balance').innerText = (user.balance || 0).toFixed(2);
                document.getElementById('hwid-input').value = user.hwid || generateRandomHWID();
            }
        }

        function showToast(msg, type = 'info') {
            const toast = document.getElementById('toast');
            const toastBox = document.getElementById('toast-box');
            const toastMsg = document.getElementById('toast-message');
            const toastIcon = document.getElementById('toast-icon');

            toastMsg.innerText = msg;
            if (type === 'error') {
                toastBox.className = "glass-panel border-l-4 border-rose-500 px-4 py-3 rounded-lg shadow-2xl flex items-center gap-3 text-sm min-w-[280px]";
                toastIcon.className = "fa-solid fa-circle-exclamation text-rose-400 text-base";
            } else if (type === 'success') {
                toastBox.className = "glass-panel border-l-4 border-emerald-500 px-4 py-3 rounded-lg shadow-2xl flex items-center gap-3 text-sm min-w-[280px]";
                toastIcon.className = "fa-solid fa-circle-check text-emerald-400 text-base";
            } else {
                toastBox.className = "glass-panel border-l-4 border-indigo-500 px-4 py-3 rounded-lg shadow-2xl flex items-center gap-3 text-sm min-w-[280px]";
                toastIcon.className = "fa-solid fa-circle-info text-indigo-400 text-base";
            }

            toast.classList.remove('translate-x-full', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-x-full', 'opacity-0');
            }, 3000);
        }

        function copyToClipboard(text, successMsg) {
            if (!text) return;
            const el = document.createElement('textarea');
            el.value = text;
            document.body.appendChild(el);
            el.select();
            document.execCommand('copy');
            document.body.removeChild(el);
            showToast(successMsg || 'คัดลอกลง Clipboard เรียบร้อย!', 'success');
        }

        // Secret Admin Portal Trigger
        function triggerSecretAdmin() {
            secretClickCount++;
            clearTimeout(secretClickTimer);
            if (secretClickCount >= 3) {
                secretClickCount = 0;
                if (isAdminUnlocked) {
                    switchTab('admin');
                } else {
                    document.getElementById('admin-modal').classList.remove('hidden');
                }
            } else {
                secretClickTimer = setTimeout(() => { secretClickCount = 0; }, 1000);
            }
        }

        function submitModalAdminPin() {
            const inputPin = document.getElementById('modal-pin-input').value.trim();
            const savedPin = localStorage.getItem(STORAGE_KEYS.ADMIN_PIN) || '1234';
            if (inputPin === savedPin) {
                unlockAdminUI();
                closeAdminModal();
                switchTab('admin');
                showToast('ปลดล็อกระบบหลังบ้านเรียบร้อย!', 'success');
            } else {
                showToast('รหัส PIN หลังบ้านไม่ถูกต้อง', 'error');
            }
        }

        function closeAdminModal() {
            document.getElementById('admin-modal').classList.add('hidden');
            document.getElementById('modal-pin-input').value = '';
        }

        function unlockAdminUI() {
            isAdminUnlocked = true;
            document.getElementById('tab-admin-btn').classList.remove('hidden');
            renderAdminPendingList();
            renderAdminKeysList();
            renderAdminCouponsList();
        }

        function lockAdmin() {
            isAdminUnlocked = false;
            document.getElementById('tab-admin-btn').classList.add('hidden');
            switchTab('getkey');
            showToast('ออกจากระบบหลังบ้านแล้ว', 'info');
        }

        // Switch View Tabs
        function switchTab(tabName) {
            if (tabName === 'admin' && !isAdminUnlocked) {
                document.getElementById('admin-modal').classList.remove('hidden');
                return;
            }

            const tabs = ['getkey', 'vip', 'wallet', 'history', 'admin'];
            tabs.forEach(t => {
                const view = document.getElementById(`view-${t}`);
                const btn = document.getElementById(`tab-${t}-btn`);
                if (view) view.classList.add('hidden');
                if (btn) {
                    btn.className = "flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 text-slate-400 hover:text-white hover:bg-slate-800/60";
                }
            });

            const activeView = document.getElementById(`view-${tabName}`);
            const activeBtn = document.getElementById(`tab-${tabName}-btn`);

            if (activeView) activeView.classList.remove('hidden');
            if (activeBtn) {
                if (tabName === 'getkey') activeBtn.className = "flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 bg-indigo-600 text-white shadow-lg shadow-indigo-600/30";
                else if (tabName === 'vip') activeBtn.className = "flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 bg-amber-600 text-white shadow-lg shadow-amber-600/30";
                else if (tabName === 'wallet') activeBtn.className = "flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 bg-emerald-600 text-white shadow-lg shadow-emerald-600/30";
                else if (tabName === 'history') activeBtn.className = "flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 bg-purple-600 text-white shadow-lg shadow-purple-600/30";
                else if (tabName === 'admin') activeBtn.className = "flex-1 py-2.5 px-3 rounded-xl font-medium text-xs sm:text-sm transition flex items-center justify-center gap-1.5 bg-rose-600 text-white shadow-lg shadow-rose-600/30";
            }

            if (tabName === 'history') renderUserHistory();
            if (tabName === 'admin') {
                renderAdminPendingList();
                renderAdminKeysList();
                renderAdminCouponsList();
            }
        }

        // Stepper Engine Logic
        function selectDuration(hours, checkpoints) {
            selectedDuration = hours;
            requiredCheckpoints = checkpoints;

            [1, 4, 12, 24].forEach(h => {
                const card = document.getElementById(`dur-${h}`);
                if (card) {
                    if (h === hours) {
                        card.className = "p-4 rounded-xl border border-indigo-500 bg-indigo-500/10 cursor-pointer transition text-center space-y-1 glow-indigo";
                    } else {
                        card.className = "p-4 rounded-xl border border-slate-800 bg-slate-900/60 hover:border-indigo-500/50 cursor-pointer transition text-center space-y-1";
                    }
                }
            });
        }

        function goToStep1() {
            document.getElementById('step-1').classList.remove('hidden');
            document.getElementById('step-2').classList.add('hidden');
        }

        function goToStep2() {
            boundHwid = document.getElementById('hwid-input').value.trim();
            completedCheckpoints = 0;
            renderCheckpointsList();
            document.getElementById('step-1').classList.add('hidden');
            document.getElementById('step-2').classList.remove('hidden');
        }

        function renderCheckpointsList() {
            const container = document.getElementById('checkpoints-list');
            if (!container) return;
            document.getElementById('checkpoint-progress-text').innerText = `${completedCheckpoints}/${requiredCheckpoints}`;

            let html = '';
            for (let i = 1; i <= requiredCheckpoints; i++) {
                const isDone = i <= completedCheckpoints;
                const isCurrent = i === completedCheckpoints + 1;

                html += `
                <div class="p-4 rounded-xl border ${isDone ? 'border-emerald-500/40 bg-emerald-500/10' : isCurrent ? 'border-indigo-500/50 bg-slate-900/80' : 'border-slate-800 bg-slate-900/30 opacity-60'} flex items-center justify-between transition">
                    <div class="flex items-center gap-3">
                        <div class="w-8 h-8 rounded-lg ${isDone ? 'bg-emerald-500/20 text-emerald-400' : 'bg-slate-800 text-slate-400'} flex items-center justify-center font-bold text-xs">
                            ${isDone ? '<i class="fa-solid fa-check"></i>' : i}
                        </div>
                        <div>
                            <span class="font-bold text-xs text-white">Checkpoint #${i}</span>
                            <p class="text-[11px] text-slate-400">${isDone ? 'ทำรายการสำเร็จแล้ว' : 'กดปุ่มเพื่อดูโฆษณาตามระยะเวลา'}</p>
                        </div>
                    </div>
                    ${isDone ? `<span class="text-xs font-bold text-emerald-400">ผ่านแล้ว</span>` : `
                        <button onclick="doCheckpoint(${i})" ${!isCurrent ? 'disabled' : ''} class="px-4 py-2 ${isCurrent ? 'bg-indigo-600 hover:bg-indigo-500 text-white shadow-lg shadow-indigo-600/20' : 'bg-slate-800 text-slate-500 cursor-not-allowed'} rounded-lg text-xs font-bold transition">
                            ทำ Checkpoint
                        </button>
                    `}
                </div>`;
            }
            container.innerHTML = html;

            const finalBtn = document.getElementById('get-key-final-btn');
            if (completedCheckpoints >= requiredCheckpoints) {
                finalBtn.disabled = false;
                finalBtn.className = "w-full py-3.5 bg-emerald-600 hover:bg-emerald-500 text-white font-bold text-sm rounded-xl transition flex items-center justify-center gap-2 shadow-lg shadow-emerald-600/30";
                finalBtn.innerHTML = `<i class="fa-solid fa-key"></i> <span>รับรหัสคีย์ฟรีทันที!</span>`;
            } else {
                finalBtn.disabled = true;
                finalBtn.className = "w-full py-3.5 bg-slate-800 text-slate-500 font-bold text-sm rounded-xl transition flex items-center justify-center gap-2 cursor-not-allowed";
                finalBtn.innerHTML = `<i class="fa-solid fa-lock"></i> <span>รับรหัสคีย์ (ทำโฆษณาให้ครบก่อน)</span>`;
            }
        }

        function doCheckpoint(num) {
            showToast(`กำลังโหลด Checkpoint #${num}...`, 'info');
            setTimeout(() => {
                completedCheckpoints = num;
                renderCheckpointsList();
                showToast(`ทำ Checkpoint #${num} สำเร็จ!`, 'success');
            }, 1000);
        }

        function generateFinalFreeKey() {
            const expireAtMs = Date.now() + (selectedDuration * 60 * 60 * 1000);
            const key = `NEXUS-FREE-${selectedDuration}H-${Math.random().toString(36).substring(2, 8).toUpperCase()}`;

            const userKeys = JSON.parse(localStorage.getItem(STORAGE_KEYS.KEYS) || '[]');
            userKeys.push({
                user: getCurrentUserData()?.username || 'Guest',
                key: key,
                type: `FREE-${selectedDuration}H`,
                hwid: boundHwid,
                expireAt: expireAtMs
            });
            localStorage.setItem(STORAGE_KEYS.KEYS, JSON.stringify(userKeys));

            document.getElementById('modal-success-title').innerText = "สร้างคีย์ฟรีสำเร็จ!";
            document.getElementById('modal-success-desc').innerText = `คีย์อายุ ${selectedDuration} ชั่วโมง ผูกกับ HWID: ${boundHwid}`;
            document.getElementById('modal-key-display').value = key;
            document.getElementById('success-modal').classList.remove('hidden');

            checkActiveFreeKey();
            goToStep1();
        }

        function checkActiveFreeKey() {
            const userKeys = JSON.parse(localStorage.getItem(STORAGE_KEYS.KEYS) || '[]');
            const currUser = getCurrentUserData()?.username || 'Guest';
            const activeKey = userKeys.find(k => k.user === currUser && k.expireAt > Date.now());

            const lockBox = document.getElementById('active-key-lock-box');
            if (activeKey) {
                document.getElementById('locked-active-key').value = activeKey.key;
                document.getElementById('locked-key-hwid').innerText = activeKey.hwid;
                const minsLeft = Math.ceil((activeKey.expireAt - Date.now()) / (1000 * 60));
                document.getElementById('locked-key-expire').innerText = `${minsLeft} นาที`;
                lockBox.classList.remove('hidden');
            } else {
                lockBox.classList.add('hidden');
            }
        }

        // VIP Purchase Methods Switching
        function selectVipPlan(plan, price) {
            activeVipPlan = plan;
            document.getElementById('plan-7d').className = plan === '7d' ? "p-5 rounded-xl border border-amber-500 bg-amber-500/10 cursor-pointer transition relative space-y-3 glow-amber" : "p-5 rounded-xl border border-slate-800 bg-slate-900/60 cursor-pointer hover:border-amber-500/40 transition relative space-y-3";
            document.getElementById('plan-life').className = plan === 'life' ? "p-5 rounded-xl border border-amber-500 bg-amber-500/10 cursor-pointer transition relative space-y-3 glow-amber" : "p-5 rounded-xl border border-slate-800 bg-slate-900/60 cursor-pointer hover:border-amber-500/40 transition relative space-y-3";
            document.getElementById('checkout-price').innerText = `฿${price}.00`;
        }

        function setPayMethod(method) {
            activePayMethod = method;
            document.getElementById('pay-opt-wallet').className = method === 'wallet' ? "p-3 rounded-xl border border-emerald-500 bg-emerald-500/10 cursor-pointer text-white font-bold text-xs flex flex-col items-center justify-center gap-1 text-center" : "p-3 rounded-xl border border-slate-800 bg-slate-900/60 cursor-pointer text-slate-400 font-bold text-xs flex flex-col items-center justify-center gap-1 text-center hover:border-slate-700";
            document.getElementById('pay-opt-truemoney').className = method === 'truemoney' ? "p-3 rounded-xl border border-orange-500 bg-orange-500/10 cursor-pointer text-white font-bold text-xs flex flex-col items-center justify-center gap-1 text-center" : "p-3 rounded-xl border border-slate-800 bg-slate-900/60 cursor-pointer text-slate-400 font-bold text-xs flex flex-col items-center justify-center gap-1 text-center hover:border-slate-700";
            document.getElementById('pay-opt-kbank').className = method === 'kbank' ? "p-3 rounded-xl border border-emerald-500 bg-emerald-500/10 cursor-pointer text-white font-bold text-xs flex flex-col items-center justify-center gap-1 text-center" : "p-3 rounded-xl border border-slate-800 bg-slate-900/60 cursor-pointer text-slate-400 font-bold text-xs flex flex-col items-center justify-center gap-1 text-center hover:border-slate-700";

            document.getElementById('pay-box-wallet').classList.toggle('hidden', method !== 'wallet');
            document.getElementById('pay-box-truemoney').classList.toggle('hidden', method !== 'truemoney');
            document.getElementById('pay-box-kbank').classList.toggle('hidden', method !== 'kbank');
        }

        function buyVipWithWallet() {
            const price = activeVipPlan === '7d' ? 50 : 150;
            const user = getCurrentUserData();

            if (!user || (user.balance || 0) < price) {
                showToast(`ยอดเงินไม่พอ (ต้องการ ฿${price})`, 'error');
                return;
            }

            updateCurrentUserData(u => { u.balance -= price; });
            const keyTag = activeVipPlan === '7d' ? 'VIP-7D' : 'VIP-LIFETIME';
            const vipKey = `NEXUS-${keyTag}-${Math.random().toString(36).substring(2, 8).toUpperCase()}`;

            const userKeys = JSON.parse(localStorage.getItem(STORAGE_KEYS.KEYS) || '[]');
            userKeys.push({
                user: user.username,
                key: vipKey,
                type: activeVipPlan === '7d' ? 'VIP (7 วัน)' : 'VIP (ถาวร)',
                hwid: user.hwid,
                expireAt: activeVipPlan === '7d' ? (Date.now() + 7 * 24 * 3600 * 1000) : 9999999999999
            });
            localStorage.setItem(STORAGE_KEYS.KEYS, JSON.stringify(userKeys));

            document.getElementById('modal-success-title').innerText = "สั่งซื้อ VIP สำเร็จ!";
            document.getElementById('modal-success-desc').innerText = `แพ็กเกจ: ${activeVipPlan === '7d' ? 'VIP 7 วัน' : 'VIP ถาวร'}`;
            document.getElementById('modal-key-display').value = vipKey;
            document.getElementById('success-modal').classList.remove('hidden');
        }

        async function submitTrueMoneyPayment() {
            const proof = document.getElementById('truemoney-link-input').value.trim();
            const fileInput = document.getElementById('truemoney-file-input');
            const imgData = await readFileAsBase64(fileInput);

            if (!proof && !imgData) {
                showToast('กรุณากรอกลิงก์ซองอั่งเปาหรือเลือกไฟล์ภาพสลิป', 'error');
                return;
            }

            const price = activeVipPlan === '7d' ? 50 : 150;
            const payments = JSON.parse(localStorage.getItem(STORAGE_KEYS.PAYMENTS) || '[]');
            payments.push({
                id: 'PAY-' + Date.now(),
                user: getCurrentUserData()?.username || 'Guest',
                channel: 'TrueMoney (VIP Purchase)',
                proof: proof || 'แนบรูปภาพสลิป',
                image: imgData,
                suggestedPrice: price,
                status: 'Pending',
                time: new Date().toLocaleString('th-TH')
            });
            localStorage.setItem(STORAGE_KEYS.PAYMENTS, JSON.stringify(payments));

            document.getElementById('truemoney-link-input').value = '';
            document.getElementById('truemoney-file-input').value = '';
            showToast('ส่งแจ้งชำระเงินเรียบร้อย รอแอนมินตรวจสอบ!', 'success');
        }

        async function submitKbankPayment() {
            const proof = document.getElementById('kbank-slip-input').value.trim();
            const fileInput = document.getElementById('kbank-file-input');
            const imgData = await readFileAsBase64(fileInput);

            if (!proof && !imgData) {
                showToast('กรุณากรอกข้อความอ้างอิงหรือแนบรูปสลิป', 'error');
                return;
            }

            const price = activeVipPlan === '7d' ? 50 : 150;
            const payments = JSON.parse(localStorage.getItem(STORAGE_KEYS.PAYMENTS) || '[]');
            payments.push({
                id: 'PAY-' + Date.now(),
                user: getCurrentUserData()?.username || 'Guest',
                channel: 'KBANK (VIP Purchase)',
                proof: proof || 'แนบรูปภาพสลิป KBANK',
                image: imgData,
                suggestedPrice: price,
                status: 'Pending',
                time: new Date().toLocaleString('th-TH')
            });
            localStorage.setItem(STORAGE_KEYS.PAYMENTS, JSON.stringify(payments));

            document.getElementById('kbank-slip-input').value = '';
            document.getElementById('kbank-file-input').value = '';
            showToast('ส่งสลิปโอนเงิน KBANK เรียบร้อย รออนุมัติ!', 'success');
        }

        // Topup Channel Methods Switching
        function setTopupMethod(method) {
            document.getElementById('topup-tab-true').className = method === 'truemoney' ? "flex-1 py-2 rounded-xl text-xs font-bold border border-orange-500 bg-orange-500/10 text-orange-300" : "flex-1 py-2 rounded-xl text-xs font-bold border border-slate-800 bg-slate-900 text-slate-400 hover:text-orange-300";
            document.getElementById('topup-tab-kbank').className = method === 'kbank' ? "flex-1 py-2 rounded-xl text-xs font-bold border border-emerald-500 bg-emerald-500/10 text-emerald-300" : "flex-1 py-2 rounded-xl text-xs font-bold border border-slate-800 bg-slate-900 text-slate-400 hover:text-emerald-300";

            document.getElementById('topup-form-true').classList.toggle('hidden', method !== 'truemoney');
            document.getElementById('topup-form-kbank').classList.toggle('hidden', method !== 'kbank');
        }

        async function submitWalletTopupTrue() {
            const proof = document.getElementById('topup-true-input').value.trim();
            const fileInput = document.getElementById('topup-true-file');
            const imgData = await readFileAsBase64(fileInput);

            if (!proof && !imgData) {
                showToast('กรุณากรอกลิงก์ซองอั่งเปาหรือแนบภาพสลิป', 'error');
                return;
            }

            const payments = JSON.parse(localStorage.getItem(STORAGE_KEYS.PAYMENTS) || '[]');
            payments.push({
                id: 'PAY-' + Date.now(),
                user: getCurrentUserData()?.username || 'Guest',
                channel: 'TrueMoney Topup',
                proof: proof || 'แนบรูปภาพสลิปเติมเงิน',
                image: imgData,
                suggestedPrice: 50,
                status: 'Pending',
                time: new Date().toLocaleString('th-TH')
            });
            localStorage.setItem(STORAGE_KEYS.PAYMENTS, JSON.stringify(payments));

            document.getElementById('topup-true-input').value = '';
            document.getElementById('topup-true-file').value = '';
            showToast('ส่งคำขอเติมเงินเรียบร้อย รอแอดมินอนุมัติ!', 'success');
        }

        async function submitWalletTopupKbank() {
            const proof = document.getElementById('topup-kbank-input').value.trim();
            const fileInput = document.getElementById('topup-kbank-file');
            const imgData = await readFileAsBase64(fileInput);

            if (!proof && !imgData) {
                showToast('กรุณากรอกเลขสลิปหรือแนบภาพสลิปโอนเงิน KBANK', 'error');
                return;
            }

            const payments = JSON.parse(localStorage.getItem(STORAGE_KEYS.PAYMENTS) || '[]');
            payments.push({
                id: 'PAY-' + Date.now(),
                user: getCurrentUserData()?.username || 'Guest',
                channel: 'KBANK Topup',
                proof: proof || 'แนบรูปภาพสลิป KBANK',
                image: imgData,
                suggestedPrice: 50,
                status: 'Pending',
                time: new Date().toLocaleString('th-TH')
            });
            localStorage.setItem(STORAGE_KEYS.PAYMENTS, JSON.stringify(payments));

            document.getElementById('topup-kbank-input').value = '';
            document.getElementById('topup-kbank-file').value = '';
            showToast('ส่งสลิป KBANK เติมเงินสำเร็จ รอแอดมินตรวจสอบ!', 'success');
        }

        function redeemBalanceCode() {
            const inputCode = document.getElementById('redeem-code-input').value.trim().toUpperCase();
            if (!inputCode) return;

            const coupons = JSON.parse(localStorage.getItem(STORAGE_KEYS.COUPONS) || '[]');
            const coupon = coupons.find(c => c.code === inputCode);

            if (!coupon) {
                showToast('ไม่พบรหัสโค้ดนี้ในระบบ', 'error');
                return;
            }

            const currUser = getCurrentUserData()?.username || 'Guest';
            if (coupon.claimedUsers && coupon.claimedUsers.includes(currUser)) {
                showToast('คุณเคยใช้โค้ดนี้ไปแล้ว', 'error');
                return;
            }

            if (coupon.claimedUsers && coupon.claimedUsers.length >= coupon.maxUsers) {
                showToast('โค้ดนี้ถูกใช้งานครบจำนวนสิทธิ์แล้ว', 'error');
                return;
            }

            if (!coupon.claimedUsers) coupon.claimedUsers = [];
            coupon.claimedUsers.push(currUser);
            localStorage.setItem(STORAGE_KEYS.COUPONS, JSON.stringify(coupons));

            updateCurrentUserData(u => { u.balance += coupon.val; });
            document.getElementById('redeem-code-input').value = '';
            showToast(`เติมโค้ดสำเร็จ! คุณได้รับเงิน ฿${coupon.val}`, 'success');
        }

        // ADMIN PENDING PAYMENTS FUNCTIONS
        function renderAdminPendingList() {
            const container = document.getElementById('admin-pending-payments-list');
            if (!container) return;
            const payments = JSON.parse(localStorage.getItem(STORAGE_KEYS.PAYMENTS) || '[]');
            const pending = payments.filter(p => p.status === 'Pending');

            document.getElementById('pending-count-badge').innerText = pending.length;

            if (pending.length === 0) {
                container.innerHTML = `<div class="p-4 text-center text-xs text-slate-500">ไม่มีรายการแจ้งชำระเงินที่รออนุมัติ</div>`;
                return;
            }

            let html = '';
            pending.forEach(p => {
                html += `
                <div class="p-4 bg-slate-950 rounded-xl border border-slate-800 space-y-3">
                    <div class="flex justify-between items-start text-xs">
                        <div>
                            <span class="font-bold text-white">${p.user}</span>
                            <span class="text-slate-400 text-[11px] block">${p.channel} | ${p.time}</span>
                        </div>
                        <span class="px-2 py-0.5 rounded-full bg-amber-500/20 text-amber-300 font-bold text-[10px]">รออนุมัติ</span>
                    </div>

                    <div class="p-2.5 bg-slate-900 rounded-lg border border-slate-800 text-xs font-mono text-cyan-300 flex items-center justify-between gap-2">
                        <span class="truncate">${p.proof}</span>
                        ${p.proof.startsWith('http') ? `
                            <button onclick="copyToClipboard('${p.proof}', 'คัดลอกลิงก์สำเร็จ!')" class="px-2 py-1 bg-slate-800 hover:bg-slate-700 text-white rounded text-[11px] shrink-0">
                                📋 คัดลอกลิงก์
                            </button>
                        ` : ''}
                    </div>

                    ${p.image ? `
                        <button onclick="viewSlipImage('${p.image}')" class="w-full py-1.5 bg-indigo-500/20 hover:bg-indigo-500/30 text-indigo-300 border border-indigo-500/30 rounded-lg text-xs font-bold flex items-center justify-center gap-1.5">
                            <i class="fa-solid fa-image"></i> กดดูรูปภาพสลิปที่แนบมา
                        </button>
                    ` : ''}

                    <div class="flex gap-2">
                        <button onclick="openApproveModal('${p.id}')" class="w-full py-2 bg-emerald-600 hover:bg-emerald-500 text-white font-bold text-xs rounded-xl shadow-lg shadow-emerald-600/20">
                            ✅ อนุมัติ & เติมเงิน
                        </button>
                    </div>
                </div>`;
            });
            container.innerHTML = html;
        }

        function openApproveModal(id) {
            activeApproveId = id;
            const payments = JSON.parse(localStorage.getItem(STORAGE_KEYS.PAYMENTS) || '[]');
            const p = payments.find(item => item.id === id);

            if (p) {
                activeApproveImgData = p.image || null;
                document.getElementById('modal-appr-user').innerText = `${p.user} (${p.channel || 'Payment'})`;
                document.getElementById('modal-appr-details').innerText = p.proof;
                document.getElementById('modal-appr-amount').value = p.suggestedPrice || 50;

                const imgPreviewBox = document.getElementById('modal-appr-img-preview');
                if (p.image) {
                    imgPreviewBox.classList.remove('hidden');
                } else {
                    imgPreviewBox.classList.add('hidden');
                }

                document.getElementById('approve-payment-modal').classList.remove('hidden');
            }
        }

        function closeApproveModal() {
            document.getElementById('approve-payment-modal').classList.add('hidden');
            activeApproveImgData = null;
        }

        function confirmPaymentApproval() {
            const amount = parseFloat(document.getElementById('modal-appr-amount').value) || 0;
            const payments = JSON.parse(localStorage.getItem(STORAGE_KEYS.PAYMENTS) || '[]');
            const p = payments.find(item => item.id === activeApproveId);

            if (p) {
                p.status = 'Approved';
                localStorage.setItem(STORAGE_KEYS.PAYMENTS, JSON.stringify(payments));

                if (p.user === getCurrentUserData()?.username) {
                    updateCurrentUserData(u => { u.balance += amount; });
                }

                showToast(`อนุมัติเติมเงิน ฿${amount} ให้คุณ ${p.user} สำเร็จ!`, 'success');
                closeApproveModal();
                renderAdminPendingList();
            }
        }

        // ADMIN KEY MANAGEMENT FUNCTIONS
        function adminCreateCustomKey() {
            const username = document.getElementById('adm-key-user').value.trim() || 'Guest';
            const typeSelect = document.getElementById('adm-key-type').value;
            let hwid = document.getElementById('adm-key-hwid').value.trim();
            if (!hwid) hwid = generateRandomHWID();

            let typeName = 'ฟรี (24 ชั่วโมง)';
            let expireAtMs = Date.now() + (24 * 60 * 60 * 1000);

            if (typeSelect === 'VIP-7D') {
                typeName = 'VIP (7 วัน)';
                expireAtMs = Date.now() + (7 * 24 * 60 * 60 * 1000);
            } else if (typeSelect === 'VIP-LIFETIME') {
                typeName = 'VIP (ถาวร)';
                expireAtMs = 9999999999999;
            }

            const keyStr = `NEXUS-${typeSelect}-${Math.random().toString(36).substring(2, 8).toUpperCase()}`;

            const keys = JSON.parse(localStorage.getItem(STORAGE_KEYS.KEYS) || '[]');
            keys.push({
                user: username,
                key: keyStr,
                type: typeName,
                hwid: hwid,
                expireAt: expireAtMs
            });
            localStorage.setItem(STORAGE_KEYS.KEYS, JSON.stringify(keys));

            document.getElementById('adm-key-user').value = '';
            document.getElementById('adm-key-hwid').value = '';
            showToast(`เสกคีย์สำเร็จ: ${keyStr}`, 'success');
            renderAdminKeysList();
            checkActiveFreeKey();
        }

        function deleteAdminKey(keyStr) {
            let keys = JSON.parse(localStorage.getItem(STORAGE_KEYS.KEYS) || '[]');
            keys = keys.filter(k => k.key !== keyStr);
            localStorage.setItem(STORAGE_KEYS.KEYS, JSON.stringify(keys));
            showToast('ลบคีย์ออกจากระบบเรียบร้อย!', 'info');
            renderAdminKeysList();
            checkActiveFreeKey();
        }

        function renderAdminKeysList() {
            const container = document.getElementById('admin-keys-list');
            if (!container) return;
            const keys = JSON.parse(localStorage.getItem(STORAGE_KEYS.KEYS) || '[]');

            document.getElementById('keys-count-badge').innerText = keys.length;

            if (keys.length === 0) {
                container.innerHTML = `<div class="p-3 text-center text-xs text-slate-500">ไม่มีรายการคีย์ในฐานข้อมูล</div>`;
                return;
            }

            let html = '';
            keys.slice().reverse().forEach(k => {
                const isExpired = k.expireAt < Date.now();
                html += `
                <div class="p-3 bg-slate-950 rounded-xl border border-slate-800 flex justify-between items-center text-xs gap-2">
                    <div class="truncate">
                        <div class="flex items-center gap-2">
                            <span class="font-bold text-white font-mono">${k.key}</span>
                            <span class="text-[10px] px-2 py-0.5 rounded-full ${k.type.includes('VIP') ? 'bg-amber-500/20 text-amber-300' : 'bg-indigo-500/20 text-indigo-300'} font-bold">${k.type}</span>
                            ${isExpired ? '<span class="text-[10px] text-rose-400 font-bold">(หมดอายุ)</span>' : ''}
                        </div>
                        <span class="text-slate-400 text-[11px] block">ผู้ใช้: ${k.user} | HWID: ${k.hwid}</span>
                    </div>
                    <div class="flex gap-1 shrink-0">
                        <button onclick="copyToClipboard('${k.key}', 'คัดลอกคีย์แล้ว!')" class="px-2.5 py-1 bg-slate-800 hover:bg-slate-700 text-slate-300 rounded text-xs font-bold">
                            📋
                        </button>
                        <button onclick="deleteAdminKey('${k.key}')" class="px-2.5 py-1 bg-rose-500/20 hover:bg-rose-500/30 text-rose-300 border border-rose-500/30 rounded text-xs font-bold">
                            🗑️ ลบ
                        </button>
                    </div>
                </div>`;
            });
            container.innerHTML = html;
        }

        // ADMIN COUPON MANAGEMENT FUNCTIONS
        function createNewCoupon() {
            const code = document.getElementById('adm-coupon-code').value.trim().toUpperCase();
            const val = parseFloat(document.getElementById('adm-coupon-val').value) || 0;
            const max = parseInt(document.getElementById('adm-coupon-max').value) || 10;

            if (!code || val <= 0) {
                showToast('กรุณากรอกชื่อโค้ดและมูลค่าเงิน', 'error');
                return;
            }

            const coupons = JSON.parse(localStorage.getItem(STORAGE_KEYS.COUPONS) || '[]');
            if (coupons.some(c => c.code === code)) {
                showToast('มีโค้ดชื่อนี้อยู่ในระบบแล้ว', 'error');
                return;
            }

            coupons.push({ code, val, maxUsers: max, claimedUsers: [] });
            localStorage.setItem(STORAGE_KEYS.COUPONS, JSON.stringify(coupons));

            document.getElementById('adm-coupon-code').value = '';
            document.getElementById('adm-coupon-val').value = '';
            document.getElementById('adm-coupon-max').value = '';
            showToast('สร้างโค้ดโปรโมชันใหม่สำเร็จ!', 'success');
            renderAdminCouponsList();
        }

        function deleteCoupon(codeStr) {
            let coupons = JSON.parse(localStorage.getItem(STORAGE_KEYS.COUPONS) || '[]');
            coupons = coupons.filter(c => c.code !== codeStr);
            localStorage.setItem(STORAGE_KEYS.COUPONS, JSON.stringify(coupons));
            showToast(`ลบโค้ด ${codeStr} เรียบร้อยแล้ว!`, 'info');
            renderAdminCouponsList();
        }

        function renderAdminCouponsList() {
            const container = document.getElementById('admin-coupons-list');
            if (!container) return;
            const coupons = JSON.parse(localStorage.getItem(STORAGE_KEYS.COUPONS) || '[]');

            document.getElementById('coupons-count-badge').innerText = coupons.length;

            if (coupons.length === 0) {
                container.innerHTML = `<div class="p-3 text-center text-xs text-slate-500">ไม่มีรายการโค้ดในระบบ</div>`;
                return;
            }

            let html = '';
            coupons.forEach(c => {
                const usedCount = c.claimedUsers ? c.claimedUsers.length : 0;
                html += `
                <div class="p-3 bg-slate-950 rounded-xl border border-slate-800 flex justify-between items-center text-xs gap-2">
                    <div>
                        <div class="flex items-center gap-2">
                            <span class="font-bold text-amber-400 font-mono text-sm">${c.code}</span>
                            <span class="text-[10px] bg-emerald-500/20 text-emerald-300 px-2 py-0.5 rounded-full font-bold">+฿${c.val}</span>
                        </div>
                        <span class="text-slate-400 text-[11px] block">สิทธิ์การใช้: ${usedCount}/${c.maxUsers} คน</span>
                    </div>
                    <div class="flex gap-1 shrink-0">
                        <button onclick="copyToClipboard('${c.code}', 'คัดลอกชื่อโค้ดแล้ว!')" class="px-2.5 py-1 bg-slate-800 hover:bg-slate-700 text-slate-300 rounded text-xs font-bold">
                            📋
                        </button>
                        <button onclick="deleteCoupon('${c.code}')" class="px-2.5 py-1 bg-rose-500/20 hover:bg-rose-500/30 text-rose-300 border border-rose-500/30 rounded text-xs font-bold">
                            🗑️ ลบ
                        </button>
                    </div>
                </div>`;
            });
            container.innerHTML = html;
        }

        function renderUserHistory() {
            const container = document.getElementById('user-history-list');
            if (!container) return;
            const keys = JSON.parse(localStorage.getItem(STORAGE_KEYS.KEYS) || '[]');
            const currUser = getCurrentUserData()?.username || 'Guest';
            const userKeys = keys.filter(k => k.user === currUser);

            if (userKeys.length === 0) {
                container.innerHTML = `<div class="p-4 text-center text-xs text-slate-500">ยังไม่มีประวัติการรับคีย์</div>`;
                return;
            }

            let html = '';
            userKeys.reverse().forEach(k => {
                html += `
                <div class="p-4 rounded-xl bg-slate-950 border border-slate-800 flex justify-between items-center gap-2">
                    <div>
                        <span class="font-bold text-white font-mono text-xs block">${k.key}</span>
                        <span class="text-[11px] text-slate-400">ประเภท: ${k.type} | HWID: ${k.hwid}</span>
                    </div>
                    <button onclick="copyToClipboard('${k.key}', 'คัดลอกคีย์สำเร็จ!')" class="px-3 py-1.5 bg-indigo-600 hover:bg-indigo-500 text-white rounded-lg text-xs font-bold shrink-0">
                        คัดลอก
                    </button>
                </div>`;
            });
            container.innerHTML = html;
        }

        // Auth Actions
        function openAuthModal() { document.getElementById('auth-modal').classList.remove('hidden'); }
        function closeAuthModal() { document.getElementById('auth-modal').classList.add('hidden'); }

        function submitAuthAction() {
            const user = document.getElementById('auth-username').value.trim();
            if (!user) return;
            const newUserObj = { username: user, balance: 0.00, hwid: generateRandomHWID() };
            localStorage.setItem(STORAGE_KEYS.CURRENT_USER, JSON.stringify(newUserObj));
            updateUserUI();
            closeAuthModal();
            showToast(`เข้าสู่ระบบในชื่อ ${user} สำเร็จ!`, 'success');
        }

        function closeSuccessModal() { document.getElementById('success-modal').classList.add('hidden'); }
    </script>
</body>
</html>
```
