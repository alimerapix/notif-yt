<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>YouTube Notification - Persiapan Kemah Besar 2026</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Arial, sans-serif;
            background: linear-gradient(135deg, #0f0f0f 0%, #1a1a1a 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 16px;
        }

        .container {
            background: #202020;
            border-radius: 20px;
            padding: 24px;
            max-width: 500px;
            width: 100%;
            box-shadow: 0 20px 60px rgba(0,0,0,0.5);
        }

        .youtube-header {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 24px;
            padding-bottom: 16px;
            border-bottom: 1px solid #3f3f3f;
        }

        .youtube-icon {
            width: 44px;
            height: 44px;
            background: #ff0000;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 26px;
        }

        h1 {
            color: white;
            font-size: 20px;
            font-weight: 600;
        }

        .notification-preview {
            background: #2a2a2a;
            border-radius: 12px;
            padding: 16px;
            margin-bottom: 24px;
            border-left: 4px solid #ff0000;
        }

        .preview-title {
            color: #ff0000;
            font-size: 12px;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .preview-content {
            color: white;
            font-size: 16px;
            font-weight: 500;
            margin-bottom: 5px;
        }

        .preview-channel {
            color: #aaa;
            font-size: 12px;
        }

        .timer-control {
            background: #2a2a2a;
            border-radius: 12px;
            padding: 16px;
            margin-bottom: 16px;
        }

        .input-group {
            margin-bottom: 16px;
        }

        label {
            display: block;
            color: #aaa;
            margin-bottom: 8px;
            font-size: 14px;
            font-weight: 500;
        }

        input {
            width: 100%;
            padding: 14px;
            background: #3f3f3f;
            border: 1px solid #5f5f5f;
            border-radius: 10px;
            color: white;
            font-size: 18px;
            font-weight: 600;
            text-align: center;
        }

        input:focus {
            outline: none;
            border-color: #ff0000;
        }

        .timer-buttons {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(70px, 1fr));
            gap: 8px;
            margin-top: 12px;
        }

        .quick-btn {
            background: #3f3f3f;
            border: none;
            color: white;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.2s;
        }

        .quick-btn:active {
            transform: scale(0.96);
            background: #ff0000;
        }

        .send-btn {
            width: 100%;
            background: #ff0000;
            color: white;
            border: none;
            padding: 16px;
            border-radius: 12px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 8px;
        }

        .send-btn:active {
            transform: scale(0.98);
            background: #cc0000;
        }

        .send-btn:disabled {
            background: #5f5f5f;
            cursor: not-allowed;
            opacity: 0.6;
        }

        .status {
            background: #2a2a2a;
            border-radius: 12px;
            padding: 16px;
            margin-top: 16px;
            text-align: center;
        }

        .status-text {
            font-weight: 600;
            margin-bottom: 5px;
            font-size: 14px;
        }

        .status-time {
            color: #aaa;
            font-size: 11px;
        }

        .countdown {
            font-size: 42px;
            font-weight: 700;
            color: #ff0000;
            margin: 10px 0;
        }

        .permission-banner {
            background: #ff000020;
            border: 1px solid #ff0000;
            border-radius: 12px;
            padding: 16px;
            margin-bottom: 16px;
            text-align: center;
        }

        .permission-banner button {
            background: #ff0000;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 10px;
            margin-top: 12px;
            cursor: pointer;
            font-weight: 600;
            font-size: 16px;
            width: 100%;
        }

        .permission-banner button:active {
            transform: scale(0.98);
        }

        .instruction {
            background: #1a1a1a;
            border-radius: 8px;
            padding: 12px;
            margin-top: 16px;
            font-size: 11px;
            color: #888;
            text-align: center;
            line-height: 1.4;
        }

        .success-icon, .error-icon {
            font-size: 20px;
            margin-right: 8px;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        .active-timer {
            animation: pulse 1s infinite;
        }

        button {
            touch-action: manipulation;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="youtube-header">
            <div class="youtube-icon">▶️</div>
            <h1>YouTube Notification</h1>
        </div>

        <div class="notification-preview">
            <div class="preview-title">🔔 NOTIFICATION PREVIEW</div>
            <div class="preview-content">VideoCreative Persiapan Kemah Besar 2026 X SIJA A</div>
            <div class="preview-channel">YouTube · VideoCreative • Baru saja</div>
        </div>

        <div id="permissionBanner" class="permission-banner" style="display: none;">
            <div>🔔 <strong>Butuh Izin Notifikasi</strong></div>
            <div style="font-size: 13px; margin-top: 8px;">Klik tombol di bawah untuk mengaktifkan notifikasi</div>
            <button id="requestPermBtn">Izinkan Notifikasi</button>
        </div>

        <div class="timer-control">
            <div class="input-group">
                <label>⏱️ Timer (detik)</label>
                <input type="number" id="timerInput" value="15" min="1" max="300">
            </div>
            
            <div class="timer-buttons">
                <button class="quick-btn" data-seconds="5">5 detik</button>
                <button class="quick-btn" data-seconds="10">10 detik</button>
                <button class="quick-btn" data-seconds="15">15 detik</button>
                <button class="quick-btn" data-seconds="30">30 detik</button>
                <button class="quick-btn" data-seconds="60">60 detik</button>
            </div>
        </div>

        <button class="send-btn" id="sendBtn" disabled>
            📢 Kirim Notifikasi
        </button>

        <div class="status" id="statusBox">
            <div class="status-text">⚡ Siap mengirim notifikasi</div>
            <div class="status-time">Klik "Izinkan Notifikasi" terlebih dahulu</div>
        </div>

        <div class="instruction">
            💡 <strong>Tips untuk HP:</strong><br>
            • Pastikan browser tidak dalam mode hemat baterai<br>
            • Buka pengaturan HP → Aplikasi → [Browser] → Izinkan notifikasi<br>
            • Notifikasi akan muncul meskipun tab di background
        </div>
    </div>

    <script>
        let timerInterval = null;
        let isTimerRunning = false;

        // Debug function
        function logStatus(message, isError = false) {
            console.log(`${new Date().toLocaleTimeString()}: ${message}`);
            const statusBox = document.getElementById('statusBox');
            const statusText = statusBox.querySelector('.status-text');
            if (statusText) {
                statusText.innerHTML = (isError ? '❌ ' : '✅ ') + message;
                statusText.style.color = isError ? '#ff4444' : '#4caf50';
            }
            const statusTime = statusBox.querySelector('.status-time');
            if (statusTime) {
                statusTime.textContent = new Date().toLocaleTimeString();
            }
        }

        // Cek dukungan notifikasi
        function checkNotificationSupport() {
            if (!('Notification' in window)) {
                logStatus('Browser tidak mendukung notifikasi!', true);
                document.getElementById('sendBtn').disabled = true;
                return false;
            }
            logStatus('Browser mendukung notifikasi');
            return true;
        }

        // Cek permission status
        function checkPermission() {
            if (!('Notification' in window)) return false;
            
            const permission = Notification.permission;
            logStatus(`Status izin: ${permission}`);
            
            const banner = document.getElementById('permissionBanner');
            const sendBtn = document.getElementById('sendBtn');
            
            if (permission === 'granted') {
                banner.style.display = 'none';
                sendBtn.disabled = false;
                sendBtn.textContent = '📢 Kirim Notifikasi';
                logStatus('Izin notifikasi aktif!');
                return true;
            } else if (permission === 'denied') {
                banner.style.display = 'block';
                sendBtn.disabled = true;
                logStatus('Izin notifikasi ditolak. Buka pengaturan browser untuk mengubahnya.', true);
                return false;
            } else {
                banner.style.display = 'block';
                sendBtn.disabled = true;
                logStatus('Menunggu izin notifikasi...');
                return false;
            }
        }

        // Minta izin notifikasi dengan cara yang lebih baik
        async function requestNotificationPermission() {
            logStatus('Meminta izin notifikasi...');
            
            if (!('Notification' in window)) {
                alert('Browser Anda tidak mendukung notifikasi');
                return false;
            }
            
            try {
                const permission = await Notification.requestPermission();
                logStatus(`Hasil izin: ${permission}`);
                
                if (permission === 'granted') {
                    document.getElementById('permissionBanner').style.display = 'none';
                    document.getElementById('sendBtn').disabled = false;
                    
                    // Test notification
                    setTimeout(() => {
                        new Notification('✅ Berhasil!', {
                            body: 'Notifikasi sudah aktif. Anda akan menerima notifikasi YouTube.',
                            icon: 'https://www.google.com/chrome/static/images/favicon.png',
                            silent: false
                        });
                    }, 500);
                    
                    return true;
                } else {
                    alert('Notifikasi tidak diizinkan. Silakan izinkan notifikasi di pengaturan browser.');
                    return false;
                }
            } catch (error) {
                logStatus(`Error: ${error.message}`, true);
                alert('Gagal meminta izin: ' + error.message);
                return false;
            }
        }

        // Kirim notifikasi
        function sendYouTubeNotification() {
            if (Notification.permission !== 'granted') {
                logStatus('Izin notifikasi belum diberikan!', true);
                return false;
            }
            
            const judul = "VideoCreative Persiapan Kemah Besar 2026 X SIJA A";
            
            const options = {
                body: "🎥 Klik untuk menonton video persiapan kemah besar 2026!",
                icon: "data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%23ff0000'%3E%3Cpath d='M10 15l5-3-5-3v6z'/%3E%3Cpath d='M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z'/%3E%3C/svg%3E",
                badge: "data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='%23ff0000'%3E%3Cpath d='M10 15l5-3-5-3v6z'/%3E%3Cpath d='M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z'/%3E%3C/svg%3E",
                tag: "youtube-kemah2026",
                renotify: true,
                requireInteraction: true,
                vibrate: [200, 100, 200],
                silent: false,
                data: {
                    url: "https://youtube.com",
                    timestamp: Date.now()
                }
            };
            
            try {
                const notification = new Notification(judul, options);
                
                notification.onclick = function(e) {
                    e.preventDefault();
                    window.open('https://youtube.com', '_blank');
                    notification.close();
                };
                
                setTimeout(() => notification.close(), 8000);
                logStatus('Notifikasi berhasil dikirim!');
                return true;
            } catch (error) {
                logStatus(`Gagal kirim notifikasi: ${error.message}`, true);
                return false;
            }
        }

        // Timer functions
        function startTimer() {
            if (Notification.permission !== 'granted') {
                logStatus('Harap izinkan notifikasi terlebih dahulu!', true);
                requestNotificationPermission();
                return;
            }
            
            if (isTimerRunning) {
                clearTimer();
                return;
            }
            
            let seconds = parseInt(document.getElementById('timerInput').value);
            if (isNaN(seconds) || seconds < 1) seconds = 15;
            if (seconds > 300) seconds = 300;
            
            startCountdown(seconds);
        }
        
        function startCountdown(seconds) {
            isTimerRunning = true;
            let remaining = seconds;
            const sendBtn = document.getElementById('sendBtn');
            const statusBox = document.getElementById('statusBox');
            
            sendBtn.textContent = `⏸️ Membatalkan (${remaining}s)`;
            
            // Buat countdown display
            let countdownDiv = document.getElementById('countdownDisplay');
            if (!countdownDiv) {
                countdownDiv = document.createElement('div');
                countdownDiv.id = 'countdownDisplay';
                countdownDiv.className = 'countdown';
                statusBox.appendChild(countdownDiv);
            }
            countdownDiv.textContent = remaining;
            
            logStatus(`Timer dimulai: ${seconds} detik`);
            
            timerInterval = setInterval(() => {
                remaining--;
                
                if (remaining <= 0) {
                    clearTimer();
                    sendYouTubeNotification();
                    logStatus('Notifikasi terkirim!');
                } else {
                    sendBtn.textContent = `⏸️ Membatalkan (${remaining}s)`;
                    if (countdownDiv) countdownDiv.textContent = remaining;
                }
            }, 1000);
        }
        
        function clearTimer() {
            if (timerInterval) {
                clearInterval(timerInterval);
                timerInterval = null;
            }
            isTimerRunning = false;
            
            const sendBtn = document.getElementById('sendBtn');
            sendBtn.textContent = '📢 Kirim Notifikasi';
            
            const countdownDiv = document.getElementById('countdownDisplay');
            if (countdownDiv) countdownDiv.remove();
        }
        
        // Setup event listeners
        function setupEventListeners() {
            // Tombol izin notifikasi
            const permBtn = document.getElementById('requestPermBtn');
            if (permBtn) {
                permBtn.onclick = (e) => {
                    e.preventDefault();
                    requestNotificationPermission();
                };
            }
            
            // Tombol kirim
            const sendBtn = document.getElementById('sendBtn');
            if (sendBtn) {
                sendBtn.onclick = (e) => {
                    e.preventDefault();
                    startTimer();
                };
            }
            
            // Tombol quick timer
            document.querySelectorAll('.quick-btn').forEach(btn => {
                btn.onclick = (e) => {
                    e.preventDefault();
                    const seconds = parseInt(btn.getAttribute('data-seconds'));
                    if (seconds) {
                        document.getElementById('timerInput').value = seconds;
                        logStatus(`Timer diatur ke ${seconds} detik`);
                    }
                };
            });
            
            // Input timer
            const timerInput = document.getElementById('timerInput');
            if (timerInput) {
                timerInput.onchange = () => {
                    let val = parseInt(timerInput.value);
                    if (isNaN(val) || val < 1) timerInput.value = 1;
                    if (val > 300) timerInput.value = 300;
                };
            }
        }
        
        // Inisialisasi
        document.addEventListener('DOMContentLoaded', () => {
            logStatus('Halaman dimuat, memeriksa notifikasi...');
            checkNotificationSupport();
            checkPermission();
            setupEventListeners();
        });
    </script>
</body>
</html>
