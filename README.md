# mm
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人知识库 | 我的资源库</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-color: #4361ee;
            --secondary-color: #3a0ca3;
            --accent-color: #4cc9f0;
            --light-color: #f8f9fa;
            --dark-color: #212529;
            --gray-color: #6c757d;
            --success-color: #4bb543;
            --border-radius: 10px;
            --box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        body {
            background-color: #f5f7ff;
            color: var(--dark-color);
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* 头部样式 */
        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 2rem 0;
            border-bottom-left-radius: 30px;
            border-bottom-right-radius: 30px;
            margin-bottom: 2rem;
            box-shadow: var(--box-shadow);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo i {
            font-size: 2.5rem;
            color: var(--accent-color);
        }

        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }

        .logo p {
            opacity: 0.9;
            font-size: 0.9rem;
        }

        .search-container {
            flex-grow: 1;
            max-width: 500px;
            margin: 20px auto 0;
            width: 100%;
            order: 3;
        }

        .search-box {
            display: flex;
            background: white;
            border-radius: 50px;
            overflow: hidden;
            padding: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .search-box input {
            flex-grow: 1;
            border: none;
            padding: 12px 20px;
            font-size: 1rem;
            outline: none;
        }

        .search-box button {
            background: var(--accent-color);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: var(--transition);
        }

        .search-box button:hover {
            background: var(--primary-color);
        }

        /* 主内容区 */
        .main-content {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            margin-bottom: 3rem;
        }

        /* 侧边栏 */
        .sidebar {
            flex: 1;
            min-width: 250px;
        }

        .categories {
            background: white;
            border-radius: var(--border-radius);
            padding: 25px;
            box-shadow: var(--box-shadow);
            margin-bottom: 25px;
        }

        .categories h3 {
            margin-bottom: 20px;
            color: var(--secondary-color);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .category-list {
            list-style: none;
        }

        .category-list li {
            padding: 12px 15px;
            margin-bottom: 10px;
            border-radius: 8px;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .category-list li:hover {
            background-color: #f0f4ff;
        }

        .category-list li.active {
            background-color: #e8edff;
            color: var(--primary-color);
            font-weight: 600;
        }

        .category-count {
            background: var(--light-color);
            padding: 3px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
        }

        /* 内容区域 */
        .content-area {
            flex: 3;
            min-width: 300px;
        }

        .content-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
            flex-wrap: wrap;
            gap: 15px;
        }

        .content-header h2 {
            color: var(--secondary-color);
        }

        .add-btn {
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: var(--transition);
        }

        .add-btn:hover {
            background: var(--secondary-color);
            transform: translateY(-3px);
        }

        /* 内容卡片网格 */
        .content-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
        }

        .content-card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
            height: 100%;
            display: flex;
            flex-direction: column;
        }

        .content-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .card-header {
            padding: 20px;
            background: linear-gradient(90deg, #f0f4ff, #e8edff);
            border-bottom: 1px solid #eaeaea;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .card-type {
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 600;
            color: var(--primary-color);
        }

        .card-date {
            font-size: 0.8rem;
            color: var(--gray-color);
        }

        .card-body {
            padding: 20px;
            flex-grow: 1;
        }

        .card-title {
            font-size: 1.2rem;
            margin-bottom: 10px;
            color: var(--dark-color);
        }

        .card-desc {
            color: var(--gray-color);
            font-size: 0.95rem;
            margin-bottom: 15px;
            line-height: 1.5;
        }

        .card-preview {
            margin: 15px 0;
            border-radius: 8px;
            overflow: hidden;
            max-height: 200px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .card-preview img, .card-preview video {
            width: 100%;
            height: auto;
            max-height: 180px;
            object-fit: cover;
        }

        .card-footer {
            padding: 15px 20px;
            border-top: 1px solid #eaeaea;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .card-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .tag {
            background: #f0f4ff;
            color: var(--primary-color);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
        }

        .card-actions {
            display: flex;
            gap: 10px;
        }

        .action-btn {
            background: none;
            border: none;
            color: var(--gray-color);
            cursor: pointer;
            transition: var(--transition);
            padding: 5px;
        }

        .action-btn:hover {
            color: var(--primary-color);
        }

        /* 空状态 */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            background: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
        }

        .empty-state i {
            font-size: 4rem;
            color: #e0e0e0;
            margin-bottom: 20px;
        }

        .empty-state h3 {
            color: var(--gray-color);
            margin-bottom: 15px;
        }

        /* 页脚 */
        footer {
            background: var(--dark-color);
            color: white;
            padding: 3rem 0 2rem;
            border-top-left-radius: 30px;
            border-top-right-radius: 30px;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 40px;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 20px;
            color: var(--accent-color);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #b0b0b0;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: white;
            padding-left: 5px;
        }

        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid #444;
            color: #b0b0b0;
            font-size: 0.9rem;
        }

        /* 响应式调整 */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .search-container {
                order: 2;
                margin-top: 20px;
            }
            
            .main-content {
                flex-direction: column;
            }
            
            .content-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- 头部区域 -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-brain"></i>
                    <div>
                        <h1>个人知识库</h1>
                        <p>我的数字资源与灵感收藏</p>
                    </div>
                </div>
                
                <div class="search-container">
                    <div class="search-box">
                        <input type="text" id="searchInput" placeholder="搜索内容、标签或类型...">
                        <button id="searchBtn"><i class="fas fa-search"></i> 搜索</button>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <!-- 主内容区域 -->
    <div class="container">
        <div class="main-content">
            <!-- 侧边栏分类 -->
            <aside class="sidebar">
                <div class="categories">
                    <h3><i class="fas fa-folder"></i> 内容分类</h3>
                    <ul class="category-list">
                        <li class="active" data-filter="all">
                            全部内容
                            <span class="category-count" id="count-all">12</span>
                        </li>
                        <li data-filter="link">
                            <i class="fas fa-link"></i> 链接
                            <span class="category-count" id="count-link">4</span>
                        </li>
                        <li data-filter="image">
                            <i class="fas fa-image"></i> 图片
                            <span class="category-count" id="count-image">3</span>
                        </li>
                        <li data-filter="video">
                            <i class="fas fa-video"></i> 视频
                            <span class="category-count" id="count-video">2</span>
                        </li>
                        <li data-filter="document">
                            <i class="fas fa-file-alt"></i> 文档/HTML
                            <span class="category-count" id="count-document">2</span>
                        </li>
                        <li data-filter="note">
                            <i class="fas fa-sticky-note"></i> 笔记
                            <span class="category-count" id="count-note">1</span>
                        </li>
                    </ul>
                </div>
                
                <div class="categories">
                    <h3><i class="fas fa-tags"></i> 热门标签</h3>
                    <div class="card-tags">
                        <span class="tag">前端开发</span>
                        <span class="tag">设计灵感</span>
                        <span class="tag">学习资源</span>
                        <span class="tag">工具推荐</span>
                        <span class="tag">技术文档</span>
                        <span class="tag">教程</span>
                    </div>
                </div>
            </aside>

            <!-- 内容展示区域 -->
            <main class="content-area">
                <div class="content-header">
                    <h2>我的知识库内容</h2>
                    <button class="add-btn" id="addContentBtn">
                        <i class="fas fa-plus"></i> 添加新内容
                    </button>
                </div>

                <!-- 内容网格 -->
                <div class="content-grid" id="contentGrid">
                    <!-- 内容卡片将通过JavaScript动态生成 -->
                </div>
                
                <!-- 空状态 -->
                <div class="empty-state" id="emptyState" style="display: none;">
                    <i class="fas fa-box-open"></i>
                    <h3>暂无内容</h3>
                    <p>尝试添加一些内容或选择其他分类</p>
                </div>
            </main>
        </div>
    </div>

    <!-- 页脚 -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>关于知识库</h3>
                    <p>这是一个个人数字资源库，用于整理和存储各种格式的优质内容，方便随时查找和使用。</p>
                </div>
                <div class="footer-section">
                    <h3>内容类型</h3>
                    <ul class="footer-links">
                        <li><a href="#">网页链接</a></li>
                        <li><a href="#">图片素材</a></li>
                        <li><a href="#">视频教程</a></li>
                        <li><a href="#">文档资料</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>静态部署</h3>
                    <ul class="footer-links">
                        <li><a href="#">GitHub Pages</a></li>
                        <li><a href="#">Vercel</a></li>
                        <li><a href="#">Netlify</a></li>
                        <li><a href="#">Cloudflare Pages</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>© 2023 个人知识库 | 静态网站，可部署到任何托管平台</p>
            </div>
        </div>
    </footer>

    <!-- 添加内容模态框（简化版，实际使用中可扩展） -->
    <div id="addContentModal" style="display: none;">
        <!-- 模态框内容将在实际应用中实现 -->
    </div>

    <script>
        // 知识库数据
        const knowledgeData = [
            {
                id: 1,
                title: "MDN Web文档",
                description: "Mozilla开发者网络，前端开发最全面的文档资源",
                type: "link",
                url: "https://developer.mozilla.org",
                tags: ["前端开发", "技术文档", "学习资源"],
                date: "2023-10-15",
                icon: "fas fa-external-link-alt"
            },
            {
                id: 2,
                title: "CSS渐变生成器",
                description: "在线生成漂亮CSS渐变背景的工具",
                type: "link",
                url: "https://cssgradient.io",
                tags: ["前端开发", "设计工具", "CSS"],
                date: "2023-10-10",
                icon: "fas fa-external-link-alt"
            },
            {
                id: 3,
                title: "Unsplash高质量图片",
                description: "免费高质量图片素材网站，适合项目使用",
                type: "image",
                preview: "https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80",
                tags: ["设计灵感", "图片素材", "资源"],
                date: "2023-10-05",
                icon: "fas fa-image"
            },
            {
                id: 4,
                title: "JavaScript教程视频",
                description: "现代JavaScript完整教程，适合初学者",
                type: "video",
                preview: "https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4",
                tags: ["前端开发", "教程", "JavaScript"],
                date: "2023-10-01",
                icon: "fas fa-video"
            },
            {
                id: 5,
                title: "前端性能优化指南",
                description: "HTML文档，包含前端性能优化的最佳实践",
                type: "document",
                url: "#",
                tags: ["前端开发", "性能优化", "技术文档"],
                date: "2023-09-28",
                icon: "fas fa-file-code"
            },
            {
                id: 6,
                title: "Vue.js官方文档",
                description: "Vue.js框架的官方文档和指南",
                type: "link",
                url: "https://vuejs.org",
                tags: ["前端开发", "Vue.js", "框架"],
                date: "2023-09-25",
                icon: "fas fa-external-link-alt"
            },
            {
                id: 7,
                title: "设计系统案例集",
                description: "收集了各大公司设计系统的截图和链接",
                type: "image",
                preview: "https://images.unsplash.com/photo-1561070791-2526d30994b5?ixlib=rb-4.0.3&auto=format&fit=crop&w-600&q=80",
                tags: ["设计灵感", "UI设计", "设计系统"],
                date: "2023-09-20",
                icon: "fas fa-image"
            },
            {
                id: 8,
                title: "CSS布局教程视频",
                description: "深入讲解Flexbox和Grid布局的教程",
                type: "video",
                preview: "https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ElephantsDream.mp4",
                tags: ["前端开发", "CSS", "教程"],
                date: "2023-09-15",
                icon: "fas fa-video"
            },
            {
                id: 9,
                title: "React组件库文档",
                description: "自定义React组件库的文档和使用示例",
                type: "document",
                url: "#",
                tags: ["前端开发", "React", "组件库"],
                date: "2023-09-10",
                icon: "fas fa-file-alt"
            },
            {
                id: 10,
                title: "GitHub前端资源合集",
                description: "GitHub上优秀的前端开发资源仓库汇总",
                type: "link",
                url: "https://github.com/topics/frontend",
                tags: ["前端开发", "GitHub", "资源"],
                date: "2023-09-05",
                icon: "fas fa-external-link-alt"
            },
            {
                id: 11,
                title: "UI动效灵感",
                description: "收集了各种优秀的UI动效设计",
                type: "image",
                preview: "https://images.unsplash.com/photo-1551650975-87deedd944c3?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80",
                tags: ["设计灵感", "UI设计", "动效"],
                date: "2023-08-30",
                icon: "fas fa-image"
            },
            {
                id: 12,
                title: "学习笔记：JavaScript闭包",
                description: "关于JavaScript闭包的概念、使用场景和示例",
                type: "note",
                content: "闭包是指有权访问另一个函数作用域中变量的函数...",
                tags: ["前端开发", "JavaScript", "学习笔记"],
                date: "2023-08-25",
                icon: "fas fa-sticky-note"
            }
        ];

        // DOM元素
        const contentGrid = document.getElementById('contentGrid');
        const searchInput = document.getElementById('searchInput');
        const searchBtn = document.getElementById('searchBtn');
        const categoryItems = document.querySelectorAll('.category-list li');
        const emptyState = document.getElementById('emptyState');
        const addContentBtn = document.getElementById('addContentBtn');
        const categoryCounts = {
            all: document.getElementById('count-all'),
            link: document.getElementById('count-link'),
            image: document.getElementById('count-image'),
            video: document.getElementById('count-video'),
            document: document.getElementById('count-document'),
            note: document.getElementById('count-note')
        };

        // 初始化页面
        document.addEventListener('DOMContentLoaded', function() {
            // 计算各类别数量
            updateCategoryCounts();
            
            // 渲染所有内容
            renderContent(knowledgeData);
            
            // 设置分类点击事件
            categoryItems.forEach(item => {
                item.addEventListener('click', function() {
                    // 更新活动状态
                    categoryItems.forEach(i => i.classList.remove('active'));
                    this.classList.add('active');
                    
                    // 根据筛选条件渲染内容
                    const filter = this.getAttribute('data-filter');
                    filterContent(filter);
                });
            });
            
            // 搜索功能
            searchBtn.addEventListener('click', performSearch);
            searchInput.addEventListener('keyup', function(event) {
                if (event.key === 'Enter') {
                    performSearch();
                }
            });
            
            // 添加内容按钮
            addContentBtn.addEventListener('click', function() {
                alert('在实际应用中，这里会打开添加内容的表单。\n\n您可以扩展此功能来添加新的链接、图片、视频等内容到您的知识库。');
            });
        });

        // 更新分类计数
        function updateCategoryCounts() {
            const counts = {
                link: 0,
                image: 0,
                video: 0,
                document: 0,
                note: 0
            };
            
            knowledgeData.forEach(item => {
                if (counts.hasOwnProperty(item.type)) {
                    counts[item.type]++;
                }
            });
            
            // 更新显示
            categoryCounts.link.textContent = counts.link;
            categoryCounts.image.textContent = counts.image;
            categoryCounts.video.textContent = counts.video;
            categoryCounts.document.textContent = counts.document;
            categoryCounts.note.textContent = counts.note;
            categoryCounts.all.textContent = knowledgeData.length;
        }

        // 渲染内容到网格
        function renderContent(data) {
            contentGrid.innerHTML = '';
            
            if (data.length === 0) {
                emptyState.style.display = 'block';
                return;
            }
            
            emptyState.style.display = 'none';
            
            data.forEach(item => {
                const card = createContentCard(item);
                contentGrid.appendChild(card);
            });
        }

        // 创建内容卡片
        function createContentCard(item) {
            const card = document.createElement('div');
            card.className = 'content-card';
            
            // 卡片头部
            const cardHeader = document.createElement('div');
            cardHeader.className = 'card-header';
            cardHeader.innerHTML = `
                <div class="card-type">
                    <i class="${item.icon}"></i>
                    <span>${getTypeName(item.type)}</span>
                </div>
                <div class="card-date">${item.date}</div>
            `;
            
            // 卡片主体
            const cardBody = document.createElement('div');
            cardBody.className = 'card-body';
            
            // 预览内容（根据类型）
            let previewHTML = '';
            if (item.type === 'image' && item.preview) {
                previewHTML = `<div class="card-preview"><img src="${item.preview}" alt="${item.title}"></div>`;
            } else if (item.type === 'video' && item.preview) {
                previewHTML = `<div class="card-preview"><video controls><source src="${item.preview}" type="video/mp4">您的浏览器不支持视频播放</video></div>`;
            }
            
            cardBody.innerHTML = `
                <h3 class="card-title">${item.title}</h3>
                <p class="card-desc">${item.description}</p>
                ${previewHTML}
            `;
            
            // 卡片底部
            const cardFooter = document.createElement('div');
            cardFooter.className = 'card-footer';
            
            // 标签
            const tagsDiv = document.createElement('div');
            tagsDiv.className = 'card-tags';
            item.tags.forEach(tag => {
                const tagSpan = document.createElement('span');
                tagSpan.className = 'tag';
                tagSpan.textContent = tag;
                tagsDiv.appendChild(tagSpan);
            });
            
            // 操作按钮
            const actionsDiv = document.createElement('div');
            actionsDiv.className = 'card-actions';
            
            // 根据内容类型添加不同的操作按钮
            if (item.type === 'link' || item.type === 'document') {
                actionsDiv.innerHTML = `
                    <button class="action-btn" title="查看" onclick="window.open('${item.url}', '_blank')">
                        <i class="fas fa-external-link-alt"></i>
                    </button>
                    <button class="action-btn" title="编辑">
                        <i class="fas fa-edit"></i>
                    </button>
                    <button class="action-btn" title="删除">
                        <i class="fas fa-trash"></i>
                    </button>
                `;
            } else {
                actionsDiv.innerHTML = `
                    <button class="action-btn" title="查看">
                        <i class="fas fa-eye"></i>
                    </button>
                    <button class="action-btn" title="编辑">
                        <i class="fas fa-edit"></i>
                    </button>
                    <button class="action-btn" title="删除">
                        <i class="fas fa-trash"></i>
                    </button>
                `;
            }
            
            cardFooter.appendChild(tagsDiv);
            cardFooter.appendChild(actionsDiv);
            
            // 组装卡片
            card.appendChild(cardHeader);
            card.appendChild(cardBody);
            card.appendChild(cardFooter);
            
            return card;
        }

        // 获取类型名称
        function getTypeName(type) {
            const typeNames = {
                'link': '链接',
                'image': '图片',
                'video': '视频',
                'document': '文档',
                'note': '笔记'
            };
            
            return typeNames[type] || type;
        }

        // 筛选内容
        function filterContent(filter) {
            if (filter === 'all') {
                renderContent(knowledgeData);
                return;
            }
            
            const filteredData = knowledgeData.filter(item => item.type === filter);
            renderContent(filteredData);
        }

        // 执行搜索
        function performSearch() {
            const searchTerm = searchInput.value.toLowerCase().trim();
            
            if (!searchTerm) {
                // 如果没有搜索词，显示当前分类的内容
                const activeFilter = document.querySelector('.category-list li.active').getAttribute('data-filter');
                filterContent(activeFilter);
                return;
            }
            
            // 搜索标题、描述和标签
            const filteredData = knowledgeData.filter(item => {
                return item.title.toLowerCase().includes(searchTerm) ||
                       item.description.toLowerCase().includes(searchTerm) ||
                       item.tags.some(tag => tag.toLowerCase().includes(searchTerm));
            });
            
            renderContent(filteredData);
            
            // 更新分类状态
            categoryItems.forEach(item => item.classList.remove('active'));
            document.querySelector('.category-list li[data-filter="all"]').classList.add('active');
        }
    </script>
</body>
</html>
