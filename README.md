# -mbti-literary-test


<!DOCTYPE html>
<html>
<head>
    <title>MBTI文学的診断</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, sans-serif;
            margin: 0;
            padding: 20px;
            background: #f0f2f5;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        h1 {
            color: #2c3e50;
            text-align: center;
        }
        button {
            background: #007AFF;
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 8px;
            font-size: 18px;
            cursor: pointer;
            margin: 10px;
            width: 100%;
        }
        .result {
            margin-top: 20px;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 8px;
            white-space: pre-wrap;
        }
        .test-case {
            background: #e8f4fd;
            padding: 15px;
            border-radius: 10px;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🎭 MBTI文学的診断</h1>
        <p>あなたの性格タイプを深く分析します</p>
        
        <div class="test-case">
            <button onclick="runTest('INFP', 15)">INFPタイプを診断</button>
            <button onclick="runTest('ENTJ', 65)">ENTJタイプを診断</button>
            <button onclick="runTest('ISFJ', 85)">ISFJタイプを診断</button>
        </div>
        
        <div id="result" class="result">
            ここに診断結果が表示されます
        </div>
    </div>

    <script>
        function runTest(mbti, divergence) {
            const texts = {
                "INFP": [
                    "あなたは夢を見ることを恐れていない。",
                    "理想と現実の境界はまだ滲んでいない。",
                    "小さな希望を拾うのが、あなたの習性だ。",
                    "他人の痛みに共鳴し、自分の痛みを詩に変える。"
                ],
                "ENTJ": [
                    "あなたは現実を支配しようとする力を持つ。",
                    "論理と結果を愛し、混沌を制御することに快感を覚える。",
                    "効率の中に美を見出し、無駄を罪とみなす。",
                    "あなたはリーダーとして尊敬されるが、同時に恐れられている。"
                ],
                "ISFJ": [
                    "あなたは世界を支える「無名の歯車」だ。",
                    "混乱を嫌い、秩序を愛する。",
                    "他者を守ることがあなたの安心であり、存在理由でもある。",
                    "現実を正しく理解し、感情を丁寧に折りたたんで暮らしている。"
                ]
            };
            
            let resultHTML = `<h2>${mbti}タイプの分析 (剥離度: ${divergence}%)</h2>`;
            
            if (divergence < 50) {
                resultHTML += `<div style="background: #CDE4F2; padding: 15px; border-radius: 8px;">`;
                resultHTML += `<p>✅ 現実適応度: まとも</p>`;
            } else if (divergence < 80) {
                resultHTML += `<div style="background: #F6C68C; padding: 15px; border-radius: 8px;">`;
                resultHTML += `<p>⚠️ 現実適応度: ちょっとダメ</p>`;
            } else {
                resultHTML += `<div style="background: #C24E4E; color: white; padding: 15px; border-radius: 8px;">`;
                resultHTML += `<p>❌ 現実適応度: 救えない</p>`;
            }
            
            texts[mbti].forEach(text => {
                resultHTML += `<p>${text}</p>`;
            });
            
            resultHTML += `</div>`;
            document.getElementById('result').innerHTML = resultHTML;
        }
        
        // ページ読み込み時にINFPを表示
        runTest('INFP', 15);
    </script>
</body>
</html>
