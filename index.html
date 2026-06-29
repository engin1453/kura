<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kura Katılım ve Çekiliş Sistemi</title>
    <style>
        :root {
            --primary-color: #0070f3;
            --success-color: #0070f3;
            --secondary-color: #ff0070;
            --background-color: #fafafa;
            --card-background: #ffffff;
            --text-color: #333333;
        }

        @media (prefers-color-scheme: dark) {
            :root {
                --background-color: #111111;
                --card-background: #1a1a1a;
                --text-color: #ffffff;
            }
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            background-color: var(--background-color);
            color: var(--text-color);
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            box-sizing: border-box;
        }

        .container {
            background: var(--card-background);
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 500px;
            box-sizing: border-box;
            margin-bottom: 20px;
        }

        h2, h3 {
            text-align: center;
            margin-top: 0;
            color: var(--primary-color);
        }

        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 6px;
            font-weight: 600;
            font-size: 14px;
        }

        input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 8px;
            box-sizing: border-box;
            background: transparent;
            color: inherit;
            font-size: 14px;
        }

        button {
            width: 100%;
            padding: 14px;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: opacity 0.2s ease;
            margin-bottom: 10px;
        }

        button:hover {
            opacity: 0.9;
        }

        .btn-register { background-color: var(--success-color); }
        .btn-draw { background-color: var(--secondary-color); }
        .btn-clear { background-color: #666; font-size: 12px; padding: 8px; }

        .counter-badge {
            text-align: center;
            font-weight: bold;
            margin: 15px 0;
            padding: 8px;
            background: rgba(0, 112, 243, 0.1);
            border-radius: 6px;
        }

        .result-container {
            margin-top: 25px;
            padding: 20px;
            background: rgba(255, 0, 112, 0.1);
            border-left: 5px solid var(--secondary-color);
            border-radius: 4px;
            display: none;
        }

        .result-container.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        .winner-list {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .winner-list li {
            padding: 12px;
            background: var(--card-background);
            margin-bottom: 8px;
            border-radius: 6px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .winner-info {
            display: flex;
            flex-direction: column;
        }

        .winner-name { font-weight: bold; }
        .winner-phone { font-size: 12px; color: #888; margin-top: 2px; }

        .winner-badge {
            background: var(--secondary-color);
            color: white;
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 12px;
            font-weight: bold;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

<div class="container">
    <h2>📝 Kura Katılım Formu</h2>
    <p style="text-align: center; font-size: 13px; color: #777;">Çekilişe katılmak için bilgilerinizi giriniz.</p>
    
    <form id="registrationForm" onsubmit="registerUser(event)">
        <div class="form-group">
            <label for="fullName">Adınız Soyadınız:</label>
            <input type="text" id="fullName" required placeholder="Örn: Ahmet Yılmaz">
        </div>

        <div class="form-group">
            <label for="phoneNumber">Telefon Numaranız:</label>
            <input type="tel" id="phoneNumber" required placeholder="Örn: 0555 XXXXXXX">
        </div>

        <button type="submit" class="btn-register">Çekilişe Katıl</button>
    </form>
</div>

<div class="container" style="border-top: 4px solid var(--secondary-color);">
    <h3>⚙️ Kura Yönetim Paneli</h3>
    
    <div class="counter-badge">
        Şu Anki Toplam Katılımcı: <span id="participantCount">0</span> Kişi
    </div>

    <div class="form-group">
        <label for="winnerCount">Kaç Kişi Kazanacak?</label>
        <input type="number" id="winnerCount" value="1" min="1">
    </div>

    <button onclick="drawLottery()" class="btn-draw">🎰 Kurayı Çek!</button>
    <button onclick="clearList()" class="btn-clear">Listeyi Sıfırla (Yeni Kura)</button>

    <div class="result-container" id="resultBox">
        <h3>🏆 Şanslı Kazananlar</h3>
        <ul class="winner-list" id="winners"></ul>
    </div>
</div>

<script>
    // Sayfa yüklendiğinde mevcut katılımcı sayısını güncelle
    document.addEventListener("DOMContentLoaded", () => {
        updateCounter();
    });

    // Katılımcıları yerel hafızadan (localStorage) al
    function getParticipants() {
        const data = localStorage.getItem("lottery_participants");
        return data ? JSON.parse(data) : [];
    }

    // Sayaç güncelleme fonksiyonu
    function updateCounter() {
        const participants = getParticipants();
        document.getElementById("participantCount").innerText = participants.length;
    }

    // Kullanıcı Kaydetme Fonksiyonu
    function registerUser(event) {
        event.preventDefault();
        
        const fullName = document.getElementById("fullName").value.trim();
        const phoneNumber = document.getElementById("phoneNumber").value.trim();

        let participants = getParticipants();

        // Aynı numarayla mükerrer kaydı önlemek için kontrol (İsteğe bağlı)
        const isAlreadyRegistered = participants.some(p => p.phone === phoneNumber);
        if (isAlreadyRegistered) {
            alert("Bu telefon numarası ile daha önce kayıt yapılmış!");
            return;
        }

        // Yeni katılımcıyı listeye ekle
        participants.push({ name: fullName, phone: phoneNumber });
        localStorage.setItem("lottery_participants", JSON.stringify(participants));

        alert("Tebrikler, kaydınız başarıyla alındı! 🎉");
        
        // Formu temizle ve sayacı güncelle
        document.getElementById("registrationForm").reset();
        updateCounter();
    }

    // Kura Çekme Fonksiyonu
    function drawLottery() {
        let participants = getParticipants();
        const winnerCountInput = document.getElementById("winnerCount");
        const count = parseInt(winnerCountInput.value) || 1;
        const resultBox = document.getElementById("resultBox");
        const winnersUl = document.getElementById("winners");

        if (participants.length === 0) {
            alert("Sistemde henüz kayıtlı katılımcı yok!");
            return;
        }

        if (count > participants.length) {
            alert(`Kazanacak kişi sayısı (${count}), toplam katılımcı sayısından (${participants.length}) fazla olamaz!`);
            return;
        }

        winnersUl.innerHTML = "<li>Kurallı çark dönüyor... 🎲</li>";
        resultBox.classList.add('active');

        // 1.5 saniyelik heyecan efekti
        setTimeout(() => {
            winnersUl.innerHTML = "";
            let winners = [];
            
            // Katılımcı dizisinin kopyasını oluştur (orijinal liste bozulmasın diye)
            let pool = [...participants];

            for (let i = 0; i < count; i++) {
                const randomIndex = Math.floor(Math.random() * pool.length);
                winners.push(pool[randomIndex]);
                pool.splice(randomIndex, 1); // Aynı kişi iki kez çıkmasın
            }

            // Sonuçları ekrana bas
            winners.forEach((winner, index) => {
                const li = document.createElement('li');
                li.innerHTML = `
                    <div class="winner-info">
                        <span class="winner-name">${winner.name}</span>
                        <span class="winner-phone">${winner.phone}</span>
                    </div>
                    <span class="winner-badge">${index + 1}. Talihli</span>
                `;
                winnersUl.appendChild(li);
            });
        }, 1500);
    }

    // Listeyi Tamamen Sıfırlama Fonksiyonu
    function clearList() {
        if (confirm("Tüm katılımcı listesini silmek istediğinize emin misiniz? Bu işlem geri alınamaz.")) {
            localStorage.removeItem("lottery_participants");
            updateCounter();
            document.getElementById("resultBox").classList.remove('active');
            alert("Katılımcı listesi sıfırlandı!");
        }
    }
</script>

</body>
</html>
