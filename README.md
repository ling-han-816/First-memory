<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body { 
      font-family: Arial, sans-serif; 
      background: linear-gradient(to right, #5B5B5B, #8E8E8E); /* 加入漸層背景 */
      color: #3C3C3C;
      margin: 0; /* 移除預設邊距 */
      height: 100vh; /* 設置頁面高度 */
      overflow: hidden; /* 隱藏滾動條 */
      transition: background 0.5s ease; /* 平滑背景轉換 */ 
    }

    /* 主要容器 */
    .main-container {
      display: flex;
      flex-direction: column; /* 垂直排列 */
      align-items: center; /* 水平置中 */
      margin: 20px; /* 外邊距 */
      height: 100%; /* 讓容器也填滿頁面 */
      justify-content: center;
    }

    /* 音樂播放器容器 */
    .audio-container {
      margin: 10px 0; /* 縮小上下邊距 */
    }

    /* 照片容器 */
    .photo-container {
      display: flex;
      justify-content: center;
      margin: 10px 0; /* 縮小上下邊距 */
    }

    /* 歌名和團名 */
    .song-info {
      font-size: 20px; /* 字體大小 */
      color: #222; /* 字體顏色 */
      margin: 4px 0; /* 調整間距 */
      text-align: center; /* 文字置中 */
      font-weight: bold; /* 設置為粗體 */
    }

    /* 歌詞容器 */
    .lyrics-container {
      margin: 20px auto;
      height: 165px;
      width: 80%;
      overflow-y: scroll;
      text-align: center;
    }

    .lyrics-container::-webkit-scrollbar {
      display: none; /* 隱藏滾動條 */
    }

    .lyrics-container {
      scrollbar-width: none; /* 隱藏 Firefox 的滾動條 */
    }

    .lyrics p {
      margin: 5px 0;
      font-size: 18px;
      line-height: 1.5;
      color: #3C3C3C;
    }

    .lyrics p.active {
      color: #fff;
      font-weight: bold;
    }

    /* 照片樣式 */
    .photo {
      width: 70%; /* 照片寬度，根據需要調整 */
      border-radius: 10px; /* 圓角邊框，根據需要調整 */
    }

    /* 背景上傳按鈕樣式 */
    .upload-container {
      margin-top: 20px;
      text-align: center;
    }
  </style>
  <title>姚曉棠&張新成_最初的記憶</title>
</head>
<body>
  <div class="main-container">
    <!-- 添加圖片 -->
    <div class="photo-container">
      <img src="data:image/webp;base64,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" alt="Song Image" class="photo"> <!-- 在這裡替換成你的圖片路徑 -->
    </div>

    <!-- 歌名和團名 -->
    <div class="song-info">最初的記憶 - 姚曉棠&張新成</div>
    
    <!-- 第一首歌 -->
    <div class="audio-container">
      <audio id="audio4" controls>
        <source src="最初的記憶.mp3" type="audio/mp3"> <!-- 第一首歌音檔 -->
      </audio>
    </div>
    
    <!-- 歌詞顯示區域 -->
    <div class="lyrics-container" id="lyrics-container4">
      <div class="lyrics" id="lyrics4">
        <p data-time="8.5">雨過天晴之后的天</p>
        <p data-time="14.8">有一點不浪漫感覺</p>
        <p data-time="22.5">一直到彩虹出現那天</p>
        <p data-time="28.6">這一刻才發現 再想一次之前</p>
        <p data-time="36.5">明明知道你會走遠 我還是拼命靠前</p>
        <p data-time="50.9">才懂到明白你已經不見</p>
        <p data-time="56.5">我還不能妥協</p>
        <p data-time="64.3">我很安靜陪著你 有些懷疑</p>
        <p data-time="72.5">能不能陪我到最終目的</p>
        <p data-time="78.5">我的安靜不懷疑 就別再提</p>
        <p data-time="87">能不能讓我回到最初的記憶</p>
        <p data-time="107.1">明明知道你會走遠</p>
        <p data-time="113.3">我還是拼命靠前</p>
        <p data-time="121.1">才懂到明白你已經不見</p>
        <p data-time="127.4">我還不能妥協</p>
        <p data-time="134.9">我很安靜陪著你</p>
        <p data-time="139.9">有些懷疑</p>
        <p data-time="143.3">能不能陪我到最終目的</p>
        <p data-time="148.9">我的安靜不懷疑</p>
        <p data-time="153.9">就別再提</p>
        <p data-time="157.5">能不能讓我回到最初的記憶</p>
        <p data-time="166.9">一直到最后都我還相信你</p>
        <p data-time="170.5">才明白這一切都只是曾經</p>
        <p data-time="174.1">我的心陪著你把自己關緊</p>
        <p data-time="181.2">不要說你還在我不會相信</p>
        <p data-time="184.7">只好等所有的情緒都穩定</p>
        <p data-time="187.9">愛情本來就想起</p>
        <p data-time="195">我很安靜陪著你 有些懷疑</p>
        <p data-time="203.2">能不能陪我 到最終目的</p>
        <p data-time="208.9">我很安靜不懷疑就別再提</p>
        <p data-time="217.2">我只想讓你回到最初的記憶</p>
      </div>
    </div>

    <!-- 背景圖片上傳 -->
    <div class="upload-container">
      <label for="bgUpload">可以自訂背景呦</label>
      <input type="file" id="bgUpload" accept="image/*">
    </div>
  </div>

<script>
    // 背景上傳處理邏輯
    const bgUpload = document.getElementById('bgUpload');
    bgUpload.addEventListener('change', function (event) {
      const file = event.target.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function (e) {
          document.body.style.backgroundImage = `url(${e.target.result})`;
          document.body.style.backgroundSize = 'cover';  // 背景圖片覆蓋整個頁面
          document.body.style.backgroundPosition = 'center';  // 圖片置中
          document.body.style.backgroundRepeat = 'no-repeat';  // 圖片不重複
        };
        reader.readAsDataURL(file); // 讀取上傳的圖片
      }
    });

    // 歌詞同步功能
    function syncLyrics(audio, lyricsElement, containerElement) {
      const lyrics = lyricsElement.getElementsByTagName('p');
      
      audio.addEventListener('timeupdate', () => {
        for (let i = 0; i < lyrics.length; i++) {
          const time = parseFloat(lyrics[i].getAttribute('data-time'));
          const nextTime = lyrics[i + 1] ? parseFloat(lyrics[i + 1].getAttribute('data-time')) : Infinity;

          if (audio.currentTime >= time && audio.currentTime < nextTime) {
            lyrics[i].classList.add('active'); // 當前歌詞變為活躍
            lyrics[i].scrollIntoView({ behavior: 'smooth', block: 'center' }); // 自動滾動並將當前歌詞居中
          } else {
            lyrics[i].classList.remove('active');
          }
        }
      });
    }

    // 對每首歌進行歌詞同步
    const audio4 = document.getElementById('audio4');
    const lyrics4 = document.getElementById('lyrics4');
    const container4 = document.getElementById('lyrics-container4');
    syncLyrics(audio4, lyrics4, container4);
  </script>

</body>
</html>
