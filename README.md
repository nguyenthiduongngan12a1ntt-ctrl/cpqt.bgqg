# cpqt.bgqg
Portfolio: Phân Định Biên Giới Vùng Biên
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio: Phân Định Biên Giới Quốc Gia</title>
    <style>
        :root {
            --primary-blue: #0A192F;
            --sea-blue: #172A45;
            --cyan: #64FFDA;
            --text-light: #CCD6F6;
            --text-gray: #8892B0;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--primary-blue);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 25, 47, 0.85);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: space-between;
            padding: 20px 50px;
            z-index: 100;
            border-bottom: 1px solid rgba(100, 255, 218, 0.1);
        }

        nav .logo {
            font-weight: bold;
            color: var(--cyan);
            font-size: 1.2rem;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 20px;
        }

        nav a {
            color: var(--text-light);
            text-decoration: none;
            transition: 0.3s;
        }

        nav a:hover {
            color: var(--cyan);
        }

        /* Hero Section */
        header {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
            position: relative;
            background: radial-gradient(circle, rgba(23,42,69,1) 0%, rgba(10,25,47,1) 100%);
        }

        header h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            color: #fff;
        }

        header p {
            color: var(--cyan);
            font-size: 1.2rem;
            max-width: 600px;
        }

        /* Giả lập sóng biển động ở Header */
        .ocean-wave {
            position: absolute;
            bottom: 0;
            width: 100%;
            height: 100px;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23172A45" fill-opacity="1" d="M0,192L48,197.3C96,203,192,213,288,192C384,171,480,117,576,112C672,107,768,149,864,165.3C960,181,1056,171,1152,149.3C1248,128,1344,96,1392,80L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-size: 1440px 100px;
            animation: waveAnimate 12s linear infinite;
        }

        @keyframes waveAnimate {
            0% { background-position-x: 0px; }
            100% { background-position-x: 1440px; }
        }

        /* Section chung */
        section {
            padding: 100px 10%;
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        h2 {
            color: var(--cyan);
            margin-bottom: 30px;
            font-size: 2rem;
            position: relative;
        }

        /* Grid hiển thị nội dung & Hình minh họa động */
        .container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .content-box {
            background: var(--sea-blue);
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 10px 30px -15px rgba(2,12,27,0.7);
        }

        ul.steps {
            list-style: none;
            margin-top: 15px;
        }

        ul.steps li {
            margin-bottom: 15px;
            position: relative;
            padding-left: 25px;
        }

        ul.steps li::before {
            content: "⚡";
            position: absolute;
            left: 0;
            color: var(--cyan);
        }

        /* --- KHU VỰC ĐỒ HỌA CHUYỂN ĐỘNG (ANIMATION CANVAS) --- */
        .visual-display {
            background: #020c1b;
            height: 350px;
            border-radius: 8px;
            position: relative;
            overflow: hidden;
            border: 1px solid rgba(100, 255, 218, 0.2);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* 1. Minh họa Biên giới đất liền (Cắm mốc) */
        .land-line {
            width: 80%;
            height: 4px;
            background: #ff4a4a;
            position: relative;
        }
        .flag-pole {
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 4px;
            height: 60px;
            background: #fff;
            transform: scaleY(0);
            transform-origin: bottom;
            animation: deployFlag 3s infinite alternate;
        }
        @keyframes deployFlag {
            0%, 30% { transform: scaleY(0); }
            70%, 100% { transform: scaleY(1); }
        }

        /* 2. Minh họa biển chồng lấn & Đường trung tuyến */
        .sea-overlap {
            width: 100%;
            height: 100%;
            display: flex;
            position: relative;
        }
        .country-a, .country-b {
            width: 60%;
            height: 100%;
            position: absolute;
            opacity: 0.6;
            transition: 2s;
        }
        .country-a {
            background: linear-gradient(90deg, #1e3c72, #2a5298);
            left: 0;
            animation: shiftLeft 4s infinite alternate ease-in-out;
        }
        .country-b {
            background: linear-gradient(270deg, #11998e, #38ef7d);
            right: 0;
            animation: shiftRight 4s infinite alternate ease-in-out;
        }
        .median-line {
            position: absolute;
            left: 50%;
            top: 0;
            width: 2px;
            height: 100%;
            background: var(--cyan);
            box-shadow: 0 0 10px var(--cyan);
            z-index: 10;
            animation: blink 1s infinite;
        }
        @keyframes shiftLeft { 0% { width: 50%; } 100% { width: 65%; } }
        @keyframes shiftRight { 0% { width: 50%; } 100% { width: 65%; } }
        @keyframes blink { 0%, 100% { opacity: 0.3; } 50% { opacity: 1; } }

        /* 3. Minh họa mặt phẳng thẳng đứng (Vùng trời / Lòng đất) */
        .vertical-axis {
            width: 100%;
            height: 100%;
            position: relative;
            background: linear-gradient(180deg, #020c1b 0%, #172a45 100%);
        }
        .ground-base {
            position: absolute;
            bottom: 30%;
            width: 100%;
            height: 10px;
            background: #8b5a2b;
        }
        .vertical-laser {
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: yellow;
            box-shadow: 0 0 15px yellow;
        }
        .scanner {
            position: absolute;
            width: 100%;
            height: 2px;
            background: rgba(100, 255, 218, 0.5);
            animation: scan 4s infinite linear;
        }
        @keyframes scan {
            0% { top: 0%; }
            100% { top: 100%; }
        }

        /* Bảng tóm tắt dạng Responsive */
        .table-wrapper {
            overflow-x: auto;
            margin-top: 40px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            background: var(--sea-blue);
            border-radius: 8px;
        }
        th, td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }
        th {
            background-color: rgba(100, 255, 218, 0.1);
            color: var(--cyan);
        }

        footer {
            text-align: center;
            padding: 40px;
            color: var(--text-gray);
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <!-- Menu Điều Hướng -->
    <nav>
        <div class="logo">BIÊN GIỚI QUỐC GIA</div>
        <ul>
            <li><a href="#co-so">Cơ Sở Chung</a></li>
            <li><a href="#tren-bo">Biên Giới Trên Bộ</a></li>
            <li><a href="#tren-bien">Biên Giới Trên Biển</a></li>
            <li><a href="#khong-dat">Vùng Trời & Lòng Đất</a></li>
        </ul>
    </nav>

    <!-- Khung mở đầu phong cách Điện Ảnh -->
    <header>
        <h1>Phân Định Biên Giới Vùng Biên</h1>
        <p>Hệ thống hóa kiến thức pháp lý và quy trình xác lập ranh giới chủ quyền quốc gia trực quan sinh động.</p>
        <div class="ocean-wave"></div>
    </header>

    <!-- I. Cơ sở chung -->
    <section id="co-so">
        <h2>I. Cơ Sở Pháp Lý Chung</h2>
        <div class="container">
            <div class="content-box">
                <p>Biên giới quốc gia là ranh giới phân định lãnh thổ quốc gia này với quốc gia khác, gồm 4 bộ phận cấu thành bất khả xâm phạm.</p>
                <ul class="steps">
                    <li>Biên giới trên bộ</li>
                    <li>Biên giới trên biển</li>
                    <li>Biên giới vùng trời</li>
                    <li>Biên giới lòng đất</li>
                </ul>
                <p style="margin-top:15px; font-style:italic; color:var(--text-gray)">* Dựa trên nguyên tắc hòa bình, tôn trọng chủ quyền và Hiến chương Liên Hợp Quốc.</p>
            </div>
            <div class="visual-display">
                <!-- Vòng tròn hiển thị 4 thành phần lãnh thổ -->
                <div style="color:var(--cyan); text-align:center; font-weight:bold;">
                    <div style="border: 2px dashed var(--cyan); padding: 30px; border-radius: 50%; animation: blink 2s infinite;">
                        CHỦ QUYỀN TOÀN VẸN<br><span style="color:#fff; font-size:0.8rem;">Đất liền - Biển - Trời - Lòng đất</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- II. Quy trình phân định biên giới trên bộ -->
    <section id="tren-bo">
        <h2>II. Quy Trình Biên Giới Trên Bộ</h2>
        <div class="container">
            <div class="content-box">
                <p>Quy trình xác định biên giới trên bộ thực tế gồm 3 bước nghiêm ngặt:</p>
                <ul class="steps">
                    <li><strong>Bước 1: Hoạch định</strong> - Ký điều ước, vẽ "đường biên giới trên giấy".</li>
                    <li><strong>Bước 2: Phân giới</strong> - Ra thực địa khảo sát, xác định vị trí thực tế.</li>
                    <li><strong>Bước 3: Cắm mốc</strong> - Đặt cột mốc cố định và lập hồ sơ pháp lý lâu dài.</li>
                </ul>
                <blockquote style="margin-top:15px; border-left: 3px solid var(--cyan); padding-left:10px; color: var(--text-gray);">
                    Ví dụ dễ nhớ: Việt Nam - Lào tiến hành hoạch định trên bản đồ trước, sau đó đoàn kỹ thuật ra thực địa đo đạc và tiến hành dựng cột mốc.
                </blockquote>
            </div>
            <div class="visual-display">
                <!-- Đồ họa cắm mốc nhảy lên -->
                <div class="land-line">
                    <div class="flag-pole">
                        <div style="width:30px; height:20px; background:red; position:absolute; left:4px; top:0; color:white; font-size:10px; font-weight:bold; text-align:center;">MỐC</div>
                    </div>
                </div>
                <div style="position:absolute; bottom:20px; color:var(--text-gray); font-size:0.9rem;">Mô phỏng: Cắm mốc thực địa (Dựng mốc từ giấy ra thực tế)</div>
            </div>
        </div>
    </section>

    <!-- III. Quy trình phân định biên giới trên biển -->
    <section id="tren-bien">
        <h2>III. Quy Trình Phân Định Biên Giới Trên Biển</h2>
        <div class="container">
            <div class="content-box">
                <p>Áp dụng theo <strong>Công ước Luật Biển UNCLOS 1982</strong>, chia làm hai kịch bản:</p>
                <ul class="steps">
                    <li><strong>Trường hợp không chồng lấn:</strong> Quốc gia tự chủ động công bố chiều rộng Lãnh hải không quá 12 hải lý tính từ Đường cơ sở.</li>
                    <li><strong>Trường hợp biển chồng lấn:</strong> (Bờ biển đối diện/liền kề): Bắt buộc đàm phán, áp dụng nguyên tắc đường trung tuyến/cách đều để đạt kết quả công bằng.</li>
                </ul>
            </div>
            <div class="visual-display">
                <!-- Đồ họa vùng chồng lấn -->
                <div class="sea-overlap">
                    <div class="country-a"><span style="margin:20px; display:inline-block;">Quốc gia A</span></div>
                    <div class="country-b"><span style="margin:20px; display:inline-block; float:right;">Quốc gia B</span></div>
                    <div class="median-line"></div>
                </div>
                <div style="position:absolute; bottom:10px; background:rgba(0,0,0,0.8); padding:5px 10px; font-size:0.8rem; color:yellow;">
                    Vùng Giao Thoa Chồng Lấn & Đường Trung Tuyến Phân Định
                </div>
            </div>
        </div>
    </section>

    <!-- IV & V. Vùng trời và Lòng Đất -->
    <section id="khong-dat">
        <h2>IV & V. Biên Giới Vùng Trời & Lòng Đất</h2>
        <div class="container">
            <div class="content-box">
                <p>Hai loại biên giới này <strong>không được phân định độc lập</strong> mà phụ thuộc hoàn toàn vào biên giới bề mặt (đất liền và biển).</p>
                <ul class="steps">
                    <li><strong>Biên giới vùng trời:</strong> Mặt phẳng thẳng đứng đi LÊN không trung (Theo Công ước Chicago 1944).</li>
                    <li><strong>Biên giới lòng đất:</strong> Mặt phẳng thẳng đứng kéo SÂU xuống tâm Trái Đất.</li>
                </ul>
                <p style="margin-top:15px; color: var(--text-gray);">Bất kỳ hành vi bay vào vùng trời hay khai thác mỏ xuyên qua mặt phẳng này khi chưa được phép đều vi phạm chủ quyền.</p>
            </div>
            <div class="visual-display">
                <!-- Đồ họa Mặt phẳng thẳng đứng -->
                <div class="vertical-axis">
                    <div class="scanner"></div>
                    <div class="vertical-laser"></div>
                    <div class="ground-base"></div>
                    <div style="position:absolute; top:15%; left:55%; font-size:0.8rem; color:#fff;">↑ VÙNG TRỜI (Đi Lên)</div>
                    <div style="position:absolute; bottom:10%; left:55%; font-size:0.8rem; color:#fff;">↓ LÒNG ĐẤT (Kéo Xuống)</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Bảng tổng hợp -->
    <section>
        <h2>VI. Bảng Tóm Tắt Hệ Thống Kiến Thức</h2>
        <div class="table-wrapper">
            <table>
                <thead>
                    <tr>
                        <th>Loại biên giới</th>
                        <th>Cách xác định</th>
                        <th>Cần thỏa thuận?</th>
                        <th>Ví dụ thực tế</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Trên bộ</strong></td>
                        <td>Hoạch định → Phân giới → Cắm mốc</td>
                        <td>Có, giữa các nước liền kề</td>
                        <td>Việt Nam – Lào thực hiện cắm mốc thực địa</td>
                    </tr>
                    <tr>
                        <td><strong>Trên biển</strong></td>
                        <td>Tính từ đường cơ sở; xử lý chồng lấn</td>
                        <td>Có nếu có vùng chồng lấn</td>
                        <td>Đàm phán đường trung tuyến vùng biển đối diện</td>
                    </tr>
                    <tr>
                        <td><strong>Vùng trời</strong></td>
                        <td>Dựng thẳng đứng lên từ nền đất/biển</td>
                        <td>Không phân định riêng</td>
                        <td>Máy bay chưa cấp phép bay qua mốc ranh giới là xâm phạm</td>
                    </tr>
                    <tr>
                        <td><strong>Lòng đất</strong></td>
                        <td>Kéo thẳng đứng xuống dưới</td>
                        <td>Không phân định riêng</td>
                        <td>Mỏ khoáng sản dưới lòng đất thuộc toàn quyền quốc gia đó</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>

    <footer>
        <p>© 2026 Trang web học tập & Portfolio Luật Quốc Tế. Thiết kế trực quan hóa tài liệu học tập.</p>
    </footer>

</body>
</html>
