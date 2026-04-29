<template>
  <section id="store" class="store">
    <div>
      <h2 class="section-title">门店信息</h2>
      <p>以下地图定位已调整到你标注的位置附近（德基大厦）。</p>
      <div class="tip" style="margin-top: 14px;">
        示例门店：南京市德基大厦（样例）<br />
        交通建议：地铁站步行约 5-8 分钟<br />
        停车提示：周边商业停车场可停放
      </div>
    </div>
    <div class="map-wrap">
      <div class="map-badge">🐾 爪爪泡泡门店位置</div>
      <div class="map-sticker map-sticker-left">🐶</div>
      <div class="map-sticker map-sticker-right">🐱</div>
      <iframe
        title="门店地图样例（德基大厦）"
        loading="lazy"
        referrerpolicy="strict-origin-when-cross-origin"
        src="https://www.openstreetmap.org/export/embed.html?bbox=118.7790%2C32.0395%2C118.7830%2C32.0435&layer=mapnik&marker=32.0415%2C118.7810"
      ></iframe>
      <div class="map-note">可爱导航提示<br />到店先洗爪再进门</div>
      <a
        class="map-nav-btn"
        href="https://www.openstreetmap.org/?mlat=32.0415&mlon=118.7810#map=18/32.0415/118.7810"
        target="_blank"
        rel="noopener noreferrer"
      >
        🦴 打开大地图
      </a>
    </div>
  </section>
</template>
