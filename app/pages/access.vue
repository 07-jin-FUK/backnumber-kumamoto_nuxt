<template>
  <div class="access-page">
    <!-- ヒーローセクション(中央配置) -->
    <div class="hero-section">
      <!-- メインビジュアル -->
      <div class="main-visual">
        <img src="/images/visual.webp" alt="Grateful Yesterdays Tour 2026" />
      </div>

      <!-- イベント情報 -->
      <section class="event-info">
        <h1 class="event-date">2026.6.27<span class="day">SAT</span> & 6.28<span class="day">SUN</span></h1>
        <p class="event-time">open.14:30 / start.17:00 / fin.19:15<span class="small">(予定)</span></p>
        <h2 class="venue-name">熊本えがお健康スタジアム</h2>
        <h3 class="page-title">アクセス方法のご案内</h3>
      </section>

      <!-- 説明文 -->
      <section class="description">
        <p>
          back number "Grateful Yesterdays Tour 2026" 開催時の熊本えがお健康スタジアムへのアクセス方法をご案内いたします。<br>各所のシャトルバス・各地からのツアーバス・電車・駐車場・徒歩でのルートなど、来場に便利な手段をご確認ください。
        </p>
      </section>
    </div>

<div class="content-wrapper">
  <!-- ナビゲーション付きの注意事項ラッパー -->
  <div class="notes-with-nav" id="notes-nav-wrapper">
    <nav class="fixed-navigation">
        <div class="nav-logo" @click="scrollToTop" style="cursor: pointer;">
          <h1>ACCESS</h1>
        </div>
        <ul class="nav-menu">
          <li :class="{ active: activeSection === 'notes' }">
            <a href="#notes" @click.prevent="scrollTo('notes')">注意事項</a>
          </li>
          <li :class="{ active: activeSection === 'map' }">
            <a href="#map" @click.prevent="scrollTo('map')">アクセスマップ</a>
          </li>
          <li :class="{ active: activeSection === 'shuttle' }">
            <a href="#shuttle" @click.prevent="scrollTo('shuttle')">シャトルバス</a>
          </li>
          <li :class="{ active: activeSection === 'park-ride' }">
            <a href="#park-ride" @click.prevent="scrollTo('park-ride')">パーク&バスライド</a>
          </li>
          <li :class="{ active: activeSection === 'tour-bus' }">
            <a href="#tour-bus" @click.prevent="scrollTo('tour-bus')">ツアーバス</a>
          </li>
          <li :class="{ active: activeSection === 'parking' }">
            <a href="#parking" @click.prevent="scrollTo('parking')">駐車場案内</a>
          </li>
          <li :class="{ active: activeSection === 'station' }">
            <a href="#station" @click.prevent="scrollTo('station')">最寄駅アクセス</a>
          </li>
          <li :class="{ active: activeSection === 'wheelchair' }">
            <a href="#wheelchair" @click.prevent="scrollTo('wheelchair')">車いすでのご来場</a>
          </li>
          <li :class="{ active: activeSection === 'faq' }">
            <a href="#faq" @click.prevent="scrollTo('faq')">よくある質問</a>
          </li>
        </ul>
      </nav>
       </div>

      <!-- メインコンテンツ -->
      <div class="main-content">
        <!-- コンテンツセクション -->
        <div class="content-sections">
          <section id="notes" class="content-section">
            <h2>注意事項</h2>
            <p class="section-intro">
              <strong>安全でスムーズなご来場のため、<span class="text-red">必ず事前にご確認</span>をお願いいたします。</strong>
            </p>
            
            <ul class="notes-list">
              <li>公演当日は、会場へ向かう周辺道路の交通規制を行います。会場内及び最寄駅、周辺道路は大変混雑致します。お時間に余裕を持って安全にご来場ください。またコンサート終演後は安全確保の為、規制退場となりますので、予めご了承ください。</li>
              
              <li>会場敷地内及び周辺施設での無断駐車、周辺道路での路上駐車は一切禁止です。</li>
              
              <li>えがお健康スタジアム(熊本県民総合運動公園)周辺は、交通規制を行います。通行証をお持ちでない車両は、コンサート準備日~本公演日まで、えがお健康スタジアム(熊本県民総合運動公園)への進入はできません。</li>
              
              <li>シャトルバス・アクセスバス・パーク&バスライドは前売り販売のみとなります。当日券の販売はございませんので、ご利用の際は必ず事前にチケットをご購入ください。なお、販売上限枚数になり次第、販売終了とさせて頂きますので予めご了承ください。</li>
              
              <li>会場周辺には送迎車乗降所はございません。会場周辺道路での送迎は、バス運行に支障をきたしますのでご遠慮ください。</li>
              
              <li>交通状況や天候により、アクセス方法が変更となる場合がございます。最新情報は<a href="https://backnumber.info/feature/stadiumtour2026" target="_blank" rel="noopener noreferrer" class="external-link">ツアー公式サイト</a>および当サイトをご確認ください。</li>
              
              <li>近隣にお住まいの方、周辺施設や周辺道路のご迷惑にならないように、皆さまのご協力をお願い致します。</li>
            </ul>
          </section>

          <section id="map" class="content-section">
            <h2>アクセスマップ</h2>
            <div class="map-info">
              <p class="venue-address">
                <strong>熊本えがお健康スタジアム</strong><br>
                〒861-8012 熊本県熊本市東区平山町2776
              </p>
            </div>
            <div class="map-container">
              <iframe 
                src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3352.3166285180846!2d130.79756217705258!3d32.83686728092274!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3540efdfaae84219%3A0xf218b5c8e7f176f6!2z44GI44GM44GK5YGl5bq344K544K_44K444Ki44Og!5e0!3m2!1sja!2sjp!4v1766535741408!5m2!1sja!2sjp"
                width="100%" 
                height="450" 
                style="border:0;" 
                allowfullscreen="" 
                loading="lazy" 
                referrerpolicy="no-referrer-when-downgrade">
              </iframe>
            </div>
            
            <div class="access-diagram">
              <img src="/images/main-all-map.png" alt="アクセス案内図" />
            </div>
          </section>

          <section id="shuttle" class="content-section">
            <h2>シャトルバスのご案内</h2>
            
            <div class="shuttle-route">
              <div class="route-description">
                <p>公演当日は、下記のバス停から熊本えがお健康スタジアムまでの直行シャトルバスを運行いたします。</p>
                <p>なお、当日券の販売はございませんので、ご利用の際は必ず事前にチケットをご購入ください。</p>
                <p>※県外からお越しのお客様は、直行シャトルバスのご利用が便利です。</p>
                <p>シャトルバスの発売詳細につきましては、決まり次第、当サイトにてご案内させていただきます。</p>
              </div>

              <div class="route-diagram">
                <img src="/images/bus-map.jpg" alt="シャトルバス路線図" />
              </div>

              <div class="route-details">
                <table class="info-table">
                  <tbody>
                  <tr>
                    <th>発車バス停</th>
                    <td>①熊本桜町バスターミナル　②熊本県庁　③芦陽才並木公園さんさん</td>
                  </tr>
                  <tr>
                    <th>所要時間</th>
                    <td>①約50分　②約35分　③約20分</td>
                  </tr>
                  <tr>
                    <th>料金</th>
                    <td>決まり次第ご案内いたします</td>
                  </tr>
                  <tr>
                    <th>運行時間</th>
                    <td>決まり次第ご案内いたします</td>
                  </tr>
                  </tbody>
                </table>
              </div>

              <div class="notice-box">
                <h4>注意事項</h4>
                <p>※チケットが片道か往復かどうかでこちらの文章は変更させます。</p>
              </div>
            </div>
          </section>

          <section id="park-ride" class="content-section">
            <h2>パーク&バスライドのご案内</h2>
            
            <div class="shuttle-route">
              <div class="route-description">
                <p>公演当日お車でお越しの場合は、下記の通り、熊本えがお健康スタジアムまでのパーク&バスライドを運行いたします。</p>
                <p>なお、当日券の販売はございませんので、ご利用の際は必ず事前にチケットをご購入ください。</p>
                <p>※自家用車でお越しのお客様は、パーク&バスライドのご利用が便利です。</p>
                <p>パーク&バスライドの発売詳細につきましては、決まり次第、当サイトにてご案内させていただきます。</p>
              </div>

              <div class="route-diagram">
                <img src="/images/bus-ride.png" alt="パーク&バスライド路線図" />
              </div>

              <div class="route-details">
                <table class="info-table">
                  <tbody>
                  <tr>
                    <th>発車駐車場</th>
                    <td>①戸島ふれあい広場　②グランメッセ熊本　③東京エレクトロン九州</td>
                  </tr>
                  <tr>
                    <th>所要時間</th>
                    <td>①約15分　②約20分　③約25分</td>
                  </tr>
                  <tr>
                    <th>料金</th>
                    <td>決まり次第ご案内いたします</td>
                  </tr>
                  <tr>
                    <th>運行時間</th>
                    <td>決まり次第ご案内いたします</td>
                  </tr>
                  </tbody>
                </table>
              </div>

              <div class="notice-box">
                <h4>注意事項</h4>
                <p>※本パーク&バスライドは、往復チケットのみの販売となっており、片道チケットの販売はございません。</p>
                <p>※駐車場は無料でご利用いただけますが、シャトルバスのチケットが必要です。</p>
              </div>
            </div>
          </section>

          <section id="tour-bus" class="content-section">
            <h2>ツアーバスのご案内</h2>
            
            <div class="tour-bus-route">
              <div class="route-description">
                <p>各日、次の9方面より日帰りでのツアーバスを運行いたします。</p>
                <p>ツアーバスの発売詳細につきましては、決まり次第、当サイトにてご案内させていただきます。</p>
              </div>

              <div class="route-diagram">
                <img src="/images/bus-tour.jpg" alt="ツアーバス路線図" />
              </div>

              <div class="notice-box">
                <h4>注意事項</h4>
                <p>※本ツアーバスは往復便での受付のみとなっており、片道(往路/復路)の販売はございません。</p>
              </div>

              <!-- 各エリアの詳細 -->
              <div class="tour-bus-details">
                <div class="area-detail">
                  <h3 class="area-title">博多駅</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>博多駅</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>

                <div class="area-detail">
                  <h3 class="area-title">小倉駅</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>小倉駅</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>

                <div class="area-detail">
                  <h3 class="area-title">熊本駅</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>熊本駅</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>

                <div class="area-detail">
                  <h3 class="area-title">佐賀駅</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>佐賀駅</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>

                <div class="area-detail">
                  <h3 class="area-title">長崎駅</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>長崎駅</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>

                <div class="area-detail">
                  <h3 class="area-title">大分駅</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>大分駅</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>

                <div class="area-detail">
                  <h3 class="area-title">宮崎駅</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>宮崎駅</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>

                <div class="area-detail">
                  <h3 class="area-title">鹿児島中央駅</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>鹿児島中央駅</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>

                <div class="area-detail">
                  <h3 class="area-title">熊本空港(往路のみ)</h3>
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>発着駅</th>
                      <td>熊本空港</td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>料金(往復)</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>決まり次第ご案内いたします</td>
                    </tr>
                    </tbody>
                  </table>
                </div>
              </div>
            </div>
          </section>

          <section id="parking" class="content-section">
            <h2>駐車場のご案内</h2>
            
            <div class="parking-info">
              <div class="route-description">
                <p>コンサートチケットをお持ちの方を対象に、駐車券(有料駐車場)を販売致します。</p>
                <p>駐車場は、〇〇〇〇となります。</p>
                <p>駐車券の発売詳細につきましては、決まり次第、当サイトにてご案内させていただきます。</p>
              </div>

              <div class="parking-fee">
                <div class="route-details">
                  <table class="info-table">
                    <tbody>
                    <tr>
                      <th>駐車券料金(1台)</th>
                      <td>
                        【駐車券】〇〇〇〇円(税込)
                      </td>
                    </tr>
                    </tbody>
                  </table>
                </div>
              </div>

              <div class="parking-map">
                <p class="map-placeholder">駐車場マップは決まり次第ご案内いたします。</p>
              </div>

<div class="notice-box">
  <h4>注意事項</h4>
  <p>※駐車場に関する詳細な注意事項は、決まり次第ご案内させていただきます。</p>
</div>
            </div>
          </section>

          <section id="station" class="content-section">
            <h2>最寄駅からのアクセス</h2>
            <p>ここに最寄駅からの情報が入ります。</p>
          </section>

          <section id="wheelchair" class="content-section">
            <h2>車いすでのご来場について</h2>
            
            <div class="wheelchair-info">
              <p class="intro-text">車いすでご来場の方へのご案内です。</p>
              
              <ul class="wheelchair-list">
                <li>◯車いす専用の駐車場(有料)をご用意致します。</li>
                <li>◯一般駐車券の購入は不要です。車いす専用駐車場券(有料)の発売詳細に関しては、決まり次第、当サイトにてご案内いたします。</li>
              </ul>
            </div>
          </section>

          <section id="faq" class="content-section">
            <h2>よくある質問</h2>
            
            <div class="faq-info">
              <p class="intro-text">ご来場に関する主なQ&Aです。お問い合わせの前にご確認ください。</p>
              
              <div class="faq-list">
                <div class="faq-item">
                  <p class="question">Q. 自転車、バイク等の駐輪場はありますか?</p>
                  <p class="answer">A. 上記に関する回答を記入いたします。</p>
                </div>

                <div class="faq-item">
                  <p class="question">Q. 妊婦なのですが、車いす専用駐車場の利用は可能でしょうか?</p>
                  <p class="answer">A. 上記に関する回答を記入いたします。</p>
                </div>

                <div class="faq-item">
                  <p class="question">Q. 公演当日、送迎は可能でしょうか?</p>
                  <p class="answer">A. 上記に関する回答を記入いたします。</p>
                </div>
              </div>
            </div>
          </section>
        </div>

        <!-- クロージングセクション -->
        <section class="closing-section">
          <p class="closing-text">
            ご来場の皆さまがスムーズにアクセスできるよう、<span>事前のご確認とチケットのご購入をお願いいたします。</span><br>公演当日は時間に余裕をもって、安全にお越しください。
          </p>
          <div class="official-link">
            <a href="https://backnumber.info/feature/stadiumtour2026" target="_blank" rel="noopener noreferrer" class="official-button">
              back number 熊本公演詳細はこちら
              <svg class="arrow" width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M1 1L7 7L1 13" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </a>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const activeSection = ref('notes')
const isTransitioning = ref(false)

const scrollTo = async (id) => {
  if (isTransitioning.value) return
  
  isTransitioning.value = true
  const mainContent = document.querySelector('.main-content')
  
  if (!mainContent) {
    isTransitioning.value = false
    return
  }
  
  // フェードアウト
  mainContent.style.opacity = '0'
  
  await new Promise(resolve => setTimeout(resolve, 300))
  
  // スクロール
  const element = document.getElementById(id)
  if (element) {
    const offset = 100 // ナビゲーション分のオフセット
    const elementPosition = element.getBoundingClientRect().top + window.pageYOffset
    const offsetPosition = elementPosition - offset
    
    window.scrollTo({
      top: offsetPosition,
      behavior: 'auto'
    })
  }
  
  await new Promise(resolve => setTimeout(resolve, 100))
  
  // フェードイン
  mainContent.style.opacity = '1'
  
  activeSection.value = id
  
  await new Promise(resolve => setTimeout(resolve, 300))
  isTransitioning.value = false
}

const scrollToTop = async () => {
  if (isTransitioning.value) return
  
  isTransitioning.value = true
  const mainContent = document.querySelector('.main-content')
  
  if (!mainContent) {
    isTransitioning.value = false
    return
  }
  
  // フェードアウト
  mainContent.style.opacity = '0'
  
  await new Promise(resolve => setTimeout(resolve, 300))
  
  // ページトップへスクロール
  window.scrollTo({ 
    top: 0,
    behavior: 'auto'
  })
  
  await new Promise(resolve => setTimeout(resolve, 100))
  
  // フェードイン
  mainContent.style.opacity = '1'
  
  activeSection.value = 'notes'
  
  await new Promise(resolve => setTimeout(resolve, 300))
  isTransitioning.value = false
}

const updateActiveSection = () => {
  if (isTransitioning.value) return
  
  const sections = ['notes', 'map', 'shuttle', 'park-ride', 'tour-bus', 'parking', 'station', 'wheelchair', 'faq']
  const windowHeight = window.innerHeight
  const documentHeight = document.documentElement.scrollHeight
  const scrollTop = window.pageYOffset || document.documentElement.scrollTop
  
  if (scrollTop + windowHeight >= documentHeight - 50) {
    activeSection.value = 'faq'
    return
  }
  
  for (const sectionId of sections) {
    const element = document.getElementById(sectionId)
    if (element) {
      const rect = element.getBoundingClientRect()
      if (rect.top <= 200 && rect.bottom >= 200) {
        activeSection.value = sectionId
        break
      }
    }
  }
}

// Intersection Observer でスクロールアニメーション
const setupScrollAnimation = () => {
  // セクション用のObserver（表示のみ管理、非表示は別で制御）
  const sectionStates = new Map()
  
  const sectionObserver = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        const id = entry.target.id
        const wasVisible = sectionStates.get(id) || false
        
        if (entry.isIntersecting && !wasVisible) {
          // 画面内に入った：表示
          entry.target.classList.add('is-visible')
          sectionStates.set(id, true)
        } else if (!entry.isIntersecting && wasVisible) {
          // 画面外に出た：非表示
          entry.target.classList.remove('is-visible')
          sectionStates.set(id, false)
        }
      })
    },
    {
      threshold: 0,
      rootMargin: '-180px 0px -180px 0px'
    }
  )

  // すべてのコンテンツセクションを監視
  const sections = document.querySelectorAll('.content-section')
  sections.forEach((section) => {
    sectionStates.set(section.id, false)
    sectionObserver.observe(section)
  })
  
// ナビゲーション用Observer
  const navigation = document.querySelector('.fixed-navigation')
  const notesSection = document.getElementById('notes')
  
  if (navigation && notesSection) {
    let isNavVisible = false
    
    const navObserver = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting && !isNavVisible) {
            navigation.classList.add('is-visible')
            isNavVisible = true
          } else if (!entry.isIntersecting && isNavVisible) {
            const rect = notesSection.getBoundingClientRect()
            if (rect.top > window.innerHeight / 2) {
              navigation.classList.remove('is-visible')
              isNavVisible = false
            }
          }
        })
      },
      {
        threshold: 0,
        rootMargin: '-150px 0px -150px 0px'
      }
    )
    
    navObserver.observe(notesSection)
  }
}

onMounted(() => {
  window.addEventListener('scroll', updateActiveSection)
  updateActiveSection()
  
  setTimeout(() => {
    setupScrollAnimation()
    
    // ページ途中でリロードした場合の初期表示チェック
    const navigation = document.querySelector('.fixed-navigation')
    const notesSection = document.getElementById('notes')
    const sections = document.querySelectorAll('.content-section')
    
    if (notesSection) {
      const rect = notesSection.getBoundingClientRect()
      // 注意事項が画面内または上にある場合はナビとセクションを表示
      if (rect.top < window.innerHeight - 150) {
        if (navigation) {
          navigation.classList.add('is-visible')
        }
      }
    }
    
    // 各セクションも初期チェック
    sections.forEach((section) => {
      const rect = section.getBoundingClientRect()
      if (rect.top < window.innerHeight - 100 && rect.bottom > 150) {
        section.classList.add('is-visible')
      }
    })
  }, 100)
})

onUnmounted(() => {
  window.removeEventListener('scroll', updateActiveSection)
  // スクロールイベントのクリーンアップは自動的に行われる
})
</script>

<style scoped>
.access-page {
  width: 100%;
  min-height: 100vh;
  background: url('/images/main-background.jpg') no-repeat center center;
  background-attachment: fixed;
  background-size: cover;
  font-family: 'Helvetica Neue', Arial, 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', Meiryo, sans-serif;
}

/* ヒーローセクション - 中央配置 */
.hero-section {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 50px 20px 0;
}

.main-visual {
  width: 100%;
  text-align: center;
  padding: 0 0 40px;
}

.main-visual img {
  max-width: 400px;
  width: 90%;
  height: auto;
}

.event-info {
  text-align: center;
  line-height: 1;
}

.event-date {
  font-size: 40px;
  font-weight: bold;
  letter-spacing: 2px;
}

.day {
  font-size: 28px;
  margin-left: 5px;
}

.event-time {
  font-size: 24px;
  font-weight: bold;
  margin: 15px 0;
  color: #333;
}

.small {
  font-size: 16px;
}

.venue-name {
  font-size: 40px;
  font-weight: bold;
  letter-spacing: 1px;
  margin-bottom: 20px;
}

.page-title {
  font-size: 40px;
  font-weight: bold;
  letter-spacing: 0.1em;
}

.description {
  max-width: 1000px;
  margin: 0 auto;
  padding: 40px 20px 60px;
  text-align: center;
}

.description p {
  line-height: 1.8;
  color: #333;
  font-size: 16px;
}

.content-wrapper {
  position: relative;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 40px 0 270px;
}


.notes-with-nav {
  position: absolute;
  left: 40px;
  top: 0;
  width: 190px;
  height: 100%;
  pointer-events: none;
}

.fixed-navigation {
  position: sticky;
  top: 50px;
  width: 190px;
  background: #fff;
  border-radius: 16px;
  padding: 20px 0 20px 20px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  z-index: 1000;
  opacity: 0;
  transition: opacity 0.8s ease;
  pointer-events: auto;
}

.fixed-navigation.is-visible {
  opacity: 1;
}
.nav-logo h1 {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 10px;
}

.nav-menu {
  list-style: none;
  padding: 0;
  margin: 0;
  padding-left: 20px;
}

.nav-menu a:hover {
  opacity: 0.6;
}

.nav-menu li {
  position: relative;
  padding-left: 0;
  line-height: 1;
}

.nav-menu li::before {
  content: "•";
  position: absolute;
  left: -20px;
  top: 50%;
  transform: translateY(-50%);
  opacity: 0;
  transition: opacity 0.3s;
  color: #333;
  font-size: 24px;
  line-height: 1;
}

.nav-menu li.active::before {
  opacity: 1;
}

.nav-menu li.active a {
  font-weight: bold;
  opacity: 1;
}

.nav-menu a {
  display: block;
  color: #333;
  text-decoration: none;
  font-size: 14px;
  font-weight: bold;
  padding: 12px 0;
  transition: opacity 0.3s;
}

/* メインコンテンツ */
.main-content {
  flex: 1;
  max-width: 1000px;
  opacity: 1;
  transition: opacity 0.3s ease;
}

/* コンテンツセクション */
.content-sections {
  width: 100%;
}

.content-section {
  padding: 80px 40px 60px;
  opacity: 0;
  transition: opacity 0.8s ease;
}

.content-section.is-visible {
  opacity: 1;
}

/* セクション背景の交互表示 */
#notes,
#shuttle,
#tour-bus,
#station,
#faq {
  background: #fff;
}

#map,
#park-ride,
#parking,
#wheelchair {
  background: transparent;
}

.content-section h2 {
  font-size: 32px;
  line-height: 1;
  margin-bottom: 60px;
  text-align: center;
}

.content-section .section-intro {
  padding-bottom: 20px;
  line-height: 1.8;
  color: #333;
  font-size: 18px;
  text-align: center;
  border-bottom: 1px solid #999;
}

.content-section p {
  line-height: 1.8;
  color: #333;
}

.notes-list {
  list-style: none;
  padding: 20px 0 0 5px;
}

.notes-list li {
  margin-bottom: 20px;
  padding-left: 1.5em;
  position: relative;
  line-height: 1.6;
  color: #333;
}

.notes-list li:before {
  content: "◯";
  position: absolute;
  left: 0;
}

.text-red {
  color: #d32f2f;
}

.external-link {
  color: #1976d2;
  text-decoration: none;
}

.external-link:hover {
  opacity: 0.7;
}

.map-info {
  text-align: center;
  margin-bottom: 30px;
}

.venue-address {
  font-size: 16px;
  line-height: 1.8;
  color: #333;
}

.venue-address strong {
  font-size: 18px;
  display: block;
  margin-bottom: 8px;
}

.map-container {
  width: 100%;
  max-width: 100%;
  margin: 0 auto;
  overflow: hidden;
}

.map-container iframe {
  display: block;
}

.access-diagram {
  width: 100%;
  max-width: 100%;
  margin: 50px auto 0;
}

.access-diagram img {
  width: 100%;
  height: auto;
  display: block;
}

.route-description {
  margin-bottom: 30px;
  line-height: 1.8;
}

.route-description p {
  margin-bottom: 12px;
}

.route-diagram {
  width: 100%;
  margin: 60px auto;
  text-align: center;
}

.route-diagram img {
  max-width: 100%;
  height: auto;
}

.route-details {
  padding: 0 0 30px;
}

.info-table {
  width: 100%;
  border-collapse: collapse;
}

.info-table th,
.info-table td {
  padding: 15px 20px 15px 0;
  text-align: left;
  border-bottom: 1px dotted #ccc;
}

.info-table th {
  width: 200px;
  font-weight: bold;
}

.info-table tr:last-child th,
.info-table tr:last-child td {
  border-bottom: none;
}



.notice-box h4 {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 10px;
}

.notice-box p {
  margin: 0;
  line-height: 1.6;
}

.tour-bus-details {
  margin-top: 40px;
}

.area-detail {
  margin-bottom: 50px;
}

.area-title {
  font-size: 22px;
  font-weight: bold;
  padding-bottom: 10px;
  border-bottom: 3px solid #333;
  margin-bottom: 20px;
  margin-left: ;
}

.parking-fee {
  margin: 40px 0;
}

.parking-map {
  margin: 40px 0;
  padding: 60px 30px;
  background: #f5f5f5;
  border-radius: 8px;
  text-align: center;
}

.map-placeholder {
  font-size: 18px;
  color: #666;
  line-height: 1.8;
}

.parking-notes {
  margin-top: 40px;
}

.parking-notes h3 {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 15px;
  padding-bottom: 10px;
  border-bottom: 2px solid #333;
}

.notes-placeholder {
  font-size: 16px;
  line-height: 1.8;
  color: #666;
}

.intro-text {
  font-size: 16px;
  line-height: 1.8;
  margin-bottom: 30px;
  padding-bottom: 20px;
  border-bottom: 1px dotted #ccc;
}

.wheelchair-list {
  list-style: none;
  padding: 0;
}

.wheelchair-list li {
  margin-bottom: 20px;
  line-height: 1.8;
  color: #333;
  font-size: 16px;
}

.faq-info .intro-text {
  font-size: 16px;
  line-height: 1.8;
  margin-bottom: 30px;
  padding-bottom: 20px;
  border-bottom: 1px dotted #ccc;
}

.faq-list {
  margin-top: 20px;
}

.faq-item {
  margin-bottom: 30px;
  padding-bottom: 30px;
  border-bottom: 1px dotted #ccc;
}

.faq-item:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

.question {
  font-size: 16px;
  font-weight: bold;
  line-height: 1.8;
  margin-bottom: 10px;
  color: #333;
}

.answer {
  font-size: 16px;
  line-height: 1.8;
  color: #333;
  margin: 0;
}

.closing-section {
  padding: 40px 30px 80px;
  text-align: center;
}

.closing-text {
  font-size: 16px;
  line-height: 1.8;
  color: #333;
  margin-bottom: 40px;
}

.official-link {
  display: flex;
  justify-content: center;
}

.official-button {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  padding: 15px 30px;
  background: #000;
  color: #fff;
  text-decoration: none;
  font-size: 16px;
  font-weight: bold;
  border-radius: 50px;
  transition: opacity 0.3s;
}

.official-button:hover {
  opacity: 0.8;
}

.official-button .arrow {
  width: 8px;
  height: 14px;
  flex-shrink: 0;
}

/* レスポンシブ対応 */
@media (max-width: 860px) {
  .content-wrapper {
    padding: 0 20px;
    flex-direction: column;
    gap: 0;
  }

  .notes-with-nav {
    position: static;
    width: 90%;
    max-width: 400px;
    margin: 20px auto;
    height: auto;
  }

  .fixed-navigation {
    position: static;
    width: 100%;
    transform: none;
  }

  .nav-menu {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
  }

  .main-content {
    max-width: 100%;
  }
}

@media (max-width: 870px) {
  .hero-section {
    padding: 30px 20px 0;
  }

  .event-date {
    font-size: 28px;
  }
  
  .venue-name,
  .page-title {
    font-size: 28px;
  }

  .nav-menu {
    grid-template-columns: 1fr;
  }

  .content-section {
    padding: 40px 20px;
  }

  .content-section h2 {
    font-size: 1.5rem;
  }

  .map-container iframe {
    height: 300px;
  }

  .closing-section {
    padding: 30px 20px 60px;
  }

  .closing-text {
    font-size: 14px;
  }

  .official-button {
    font-size: 14px;
    padding: 15px 30px;
  }
}
</style>
