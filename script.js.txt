// 页面加载完成后执行
document.addEventListener('DOMContentLoaded', function() {
    console.log('网站已加载完成！');
    
    // 为所有标签添加点击效果
    const tags = document.querySelectorAll('.tag');
    tags.forEach(tag => {
        tag.addEventListener('click', function() {
            alert('你点击了：' + this.textContent);
        });
    });
    
    // 为项目卡片添加点击效果
    const projectCards = document.querySelectorAll('.project-card');
    projectCards.forEach(card => {
        card.addEventListener('click', function() {
            const title = this.querySelector('h4').textContent;
            alert('查看项目：' + title);
        });
    });
    
    // 显示当前时间
    const timeElement = document.createElement('p');
    timeElement.className = 'current-time';
    timeElement.style.cssText = 'text-align:center;margin-top:10px;color:#666;font-size:0.9rem;';
    
    function updateTime() {
        const now = new Date();
        timeElement.textContent = '当前时间：' + now.toLocaleString('zh-CN');
    }
    
    updateTime();
    setInterval(updateTime, 1000);
    
    // 将时间显示添加到页脚
    const footer = document.querySelector('footer');
    footer.insertBefore(timeElement, footer.querySelector('.hint'));
    
    // 欢迎消息
    setTimeout(() => {
        console.log('✨ 网站已准备就绪！');
    }, 1000);
});