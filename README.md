<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>图片压缩工具 - 苹果风格设计</title>
    <link rel="stylesheet" href="styles.css">
    <!-- 添加苹果字体 -->
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=SF+Pro+Display:wght@400;500;600&display=swap">
</head>
<body>
    <div class="container">
        <!-- 头部区域 -->
        <header>
            <h1>图片压缩工具</h1>
            <p>简单高效的在线图片压缩，保持视觉效果的同时减小文件体积</p>
        </header>

        <!-- 主要内容区域 -->
        <main>
            <!-- 上传区域 -->
            <section class="upload-section" id="upload-area">
                <div class="upload-container" id="drop-area">
                    <img src="icons/upload-icon.svg" alt="上传图标" id="upload-icon">
                    <p>拖放图片到这里或<label for="file-input" class="file-label">选择文件</label></p>
                    <p class="file-types">支持 PNG、JPG、JPEG 等格式，最多可选择10张图片</p>
                    <input type="file" id="file-input" accept="image/*" multiple hidden>
                </div>
            </section>

            <!-- 图片处理区域 (初始隐藏) -->
            <section class="image-processing" id="image-processing">
                <div class="controls">
                    <div class="control-group">
                        <label for="quality-slider">压缩质量</label>
                        <input type="range" id="quality-slider" min="0" max="100" value="80" class="slider">
                        <span id="quality-value">80%</span>
                    </div>
                    <p class="slider-tip">向左拖动减小文件大小，但可能降低图片质量；向右拖动提高图片质量，但文件大小会增加</p>
                    <div class="control-group">
                        <label for="max-width">最大宽度 (像素)</label>
                        <input type="number" id="max-width" min="100" step="50" value="1920" class="number-input">
                    </div>
                    <div class="button-group">
                        <button id="compress-btn" class="primary-btn">压缩图片</button>
                        <button id="reset-btn" class="secondary-btn">重新上传</button>
                    </div>
                </div>

                <!-- 加载动画 -->
                <div id="loading-spinner" class="loading-spinner">
                    <div class="spinner"></div>
                    <p>正在压缩图片，请稍候...</p>
                </div>

                <!-- 批量处理区域 -->
                <div id="batch-processing" class="batch-processing">
                    <div class="batch-header">
                        <h3>批量处理 (<span id="processed-count">0</span>/<span id="total-count">0</span>)</h3>
                        <div class="batch-actions">
                            <button id="compress-all-btn" class="primary-btn">压缩全部</button>
                            <button id="download-all-btn" class="secondary-btn">下载全部</button>
                        </div>
                    </div>
                    <div id="images-grid" class="images-grid">
                        <!-- 图片项将通过JavaScript动态添加 -->
                    </div>
                </div>

                <div class="preview-container">
                    <div class="preview-box">
                        <h3>原始图片</h3>
                        <div class="image-container" id="original-container">
                            <img id="original-image" alt="原始图片预览">
                        </div>
                        <div class="file-info">
                            <p>大小: <span id="original-size">-</span></p>
                            <p>尺寸: <span id="original-dimensions">-</span></p>
                        </div>
                    </div>
                    <div class="preview-box">
                        <h3>压缩后图片</h3>
                        <div class="image-container" id="compressed-container">
                            <img id="compressed-image" alt="压缩后图片预览">
                        </div>
                        <div class="file-info">
                            <p>大小: <span id="compressed-size">-</span></p>
                            <p>尺寸: <span id="compressed-dimensions">-</span></p>
                            <p>节省: <span id="size-saving">-</span> (<span id="size-saving-percent">-</span>)</p>
                        </div>
                        <a id="download-btn" class="secondary-btn" download="compressed-image.jpg">下载压缩图片</a>
                    </div>
                </div>
            </section>
        </main>

        <!-- 页脚区域 -->
        <footer>
            <p>© 2023 图片压缩工具 | 使用HTML5和JavaScript开发，无需上传至服务器，保护您的隐私</p>
        </footer>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.10.1/jszip.min.js"></script>
    <script src="script.js"></script>
</body>
</html> 
