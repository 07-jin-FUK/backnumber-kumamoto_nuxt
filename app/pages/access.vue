<template>
  <div class="access-page">
      <!-- ローディングオーバーレイ -->
  <div class="loading-overlay" :class="{ active: isLoading }">
    <img src="/images/logo-text-black.png" alt="Loading" class="loading-logo" />
  </div>
    <!-- ハンバーガーメニューボタン (860px以下で表示) -->
    <button 
      class="hamburger-button" 
      :class="{ active: isMenuOpen }"
      @click="toggleMenu"
      aria-label="メニュー"
    >
      <span></span>
      <span></span>
      <span></span>
    </button>

    <!-- モバイルメニューオーバーレイ -->
    <div class="mobile-menu-overlay" :class="{ active: isMenuOpen }" @click="closeMenu"></div>

<!-- ヒーローセクション(中央配置) - ここまでで800px -->
    <div class="hero-section">
      <!-- メインビジュアル -->
      <div class="main-visual">
        <img src="/images/visual.webp" alt="Grateful Yesterdays Tour 2026" />
      </div>

      <!-- イベント情報 -->
      <section class="event-info">
        <h1 class="event-date">
          2026.6.27<span class="day">[SAT]</span>
          & 6.28<span class="day">[SUN]</span>
        </h1>
        <p class="event-time">
          open.14:30 / start.17:00 / fin.19:15
          <span class="small">(予定)</span>
        </p>
        <h2 class="venue-name">熊本えがお健康スタジアム</h2>
        <h3 class="page-title">アクセス方法のご案内</h3>
      </section>
    </div>

    <!-- 説明文 - hero-sectionの外に移動 -->
    <section class="description">
      <p>
        <span class="sp">back number "Grateful Yesterdays Tour 2026" <span class="tab step">開催時の熊本えがお健康スタジアムへのアクセス方法をご案内いたします。</span></span>
        <br />
        各所のシャトルバス・各地からのツアーバス・電車・パーク&バスライド・徒歩でのルートなど、<span class="tab step">来場に便利な手段をご確認ください。</span>
      </p>
    </section>

    <div class="content-wrapper">
      <!-- ナビゲーション付きの注意事項ラッパー -->
      <div class="notes-with-nav" id="notes-nav-wrapper">
<nav class="fixed-navigation" :class="{ 'mobile-open': isMenuOpen }">
  <div class="nav-logo" @click="scrollToTop" style="cursor: pointer">
    <img src="/images/logo-text.png" alt="ACCESS" class="nav-logo-image" />
  </div>
  <ul class="nav-menu">
    <li :class="{ active: activeSection === 'notes' }">
      <a href="#notes" @click.prevent="handleNavClick('notes')">注意事項</a>
    </li>
            <li :class="{ active: activeSection === 'map' }">
              <a href="#map" @click.prevent="handleNavClick('map')">アクセスマップ</a>
            </li>
            <li :class="{ active: activeSection === 'shuttle' }">
              <a href="#shuttle" @click.prevent="handleNavClick('shuttle')">シャトルバス</a>
            </li>
            <li :class="{ active: activeSection === 'park-ride' }">
              <a href="#park-ride" @click.prevent="handleNavClick('park-ride')">パーク&バスライド</a>
            </li>
            <li :class="{ active: activeSection === 'tour-bus' }">
              <a href="#tour-bus" @click.prevent="handleNavClick('tour-bus')">ツアーバス</a>
            </li>
            <li :class="{ active: activeSection === 'parking' }">
              <a href="#parking" @click.prevent="handleNavClick('parking')">乗降所案内</a>
            </li>
            <li :class="{ active: activeSection === 'station' }">
              <a href="#station" @click.prevent="handleNavClick('station')">最寄駅アクセス</a>
            </li>
            <li :class="{ active: activeSection === 'wheelchair' }">
              <a href="#wheelchair" @click.prevent="handleNavClick('wheelchair')">車いすでのご来場</a>
            </li>
            <li :class="{ active: activeSection === 'faq' }">
              <a href="#faq" @click.prevent="handleNavClick('faq')">よくある質問</a>
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
              <strong>
                安全でスムーズなご来場のため、<span class="sp step">
                <span class="text-red">必ず事前にご確認</span>
                をお願いいたします。</span>
                <span class="sp-none"><br></span>
                <span class="text-red">自家用車でのご来場は一切できません。<br>
また会場周辺は当日交通規制が入り、<span class="sp step">送迎車の立ち入りもできなくなります。</span></span>
              </strong>
            </p>

            <ul class="notes-list">
              <li>公演当日は、会場へ向かう周辺道路の交通規制を行います。会場内及び最寄駅、周辺道路は大変混雑致します。お時間に余裕を持って安全にご来場ください。またコンサート終演後は安全確保の為、規制退場となりますので、予めご了承ください。</li>

              <li>会場敷地内及び周辺施設での無断駐車、周辺道路での路上駐車は一切禁止です。</li>

              <li>えがお健康スタジアム(熊本県民総合運動公園)周辺は、交通規制を行います。通行証をお持ちでない車両は、コンサート準備日~本公演日まで、えがお健康スタジアム(熊本県民総合運動公園)への進入はできません。</li>

              <li>シャトルバス・ツアーバス・パーク&バスライドは前売り販売のみとなります。当日券の販売はございませんので、ご利用の際は必ず事前にチケットをご購入ください。なお、販売上限枚数になり次第、販売終了とさせて頂きますので予めご了承ください。</li>

              <li>
                会場周辺には
                <strong>送迎車乗降所</strong>
                はございません。会場周辺道路での送迎は、バス運行に支障をきたしますのでご遠慮ください。
              </li>

              <li>
                交通状況や天候により、アクセス方法が変更となる場合がございます。最新情報は
                <a href="https://backnumber.info/feature/stadiumtour2026" target="_blank" rel="noopener noreferrer" class="external-link">ツアー公式サイト</a>
                および当サイトをご確認ください。
              </li>

              <li>近隣にお住まいの方、周辺施設や周辺道路のご迷惑にならないように、皆さまのご協力をお願い致します。</li>
            </ul>
          </section>

          <section id="map" class="content-section">
            <h2>アクセスマップ</h2>
            <div class="map-info">
              <p class="venue-address">
                <strong>熊本えがお健康スタジアム</strong>
                <span>〒861-8012 熊本県熊本市東区平山町2776</span>
              </p>
            </div>
            <div class="map-container">
              <iframe
                src="https://www.google.com/maps/embed?pb=!1m10!1m8!1m3!1d3606.28135161495!2d130.80049813873242!3d32.8373622716585!3m2!1i1024!2i768!4f13.1!5e0!3m2!1sja!2sjp!4v1766627064954!5m2!1sja!2sjp"
                width="100%"
                height="500px"
                style="border: 0"
                allowfullscreen=""
                loading="lazy"
                referrerpolicy="no-referrer-when-downgrade"
              ></iframe>
            </div>

            <div class="access-diagram">
              <img src="/images/access-all.png" alt="アクセス案内図" />
            </div>
          </section>

          <section id="shuttle" class="content-section">
            <h2>シャトルバスのご案内</h2>

            <div class="shuttle-route">
              <div class="route-description">
                <p>公演当日は次の3方面より会場直行シャトルバスを運行いたします。</p>
                <p class="red no-under"><strong>当日券の販売はございませんので、ご利用の際は必ず事前にチケットをご購入ください。</strong></p>
                <p>なお、各シャトルバスは、混雑緩和のため出発時間帯を区切っての販売となります。</p>
                <p>時間帯毎に販売数に限りがございますので、予めご了承ください。</p>
              </div>

              <div class="route-diagram">
                <img src="/images/bus-map.png" alt="シャトルバス路線図" />
              </div>

              <div class="route-details">
                <table class="info-table">
                  <tbody>
                    <tr>
                      <th>発車バス停</th>
                      <td>①熊本桜町バスターミナル　<span class="sp tab block">②熊本県庁　</span><span class="sp tab">③菊陽杉並木公園さんさん</span></td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>①約 50 分　②約 35 分　③約 20 分</td>
                    </tr>
                    <tr>
                      <th>料金</th>
                      <td>※1期販売（〜4/26（日）まで）<br>
                        ＜おとな＞<br>
                        ①往復券 6,000 円、片道券 3,300 円<br>②往復券 4,000 円、片道券 2,300 円<br>③往復券 3,000 円、片道券 1,800 円<br><br>
                    
                        ＜こども＞<br>
                        ①往復券 3,000 円、片道券 1,800 円<br>②往復券 2,000 円、片道券 1,300 円<br>③往復券 1,500 円、片道券 1,000 円<br><br>
                    ※2期販売（4/27（月）〜）<br>
                        ＜おとな＞<br>
                        ①往復券 8,000 円、片道券 4,300 円<br>②往復券 6,000 円、片道券 3,300 円<br>③往復券 5,000 円、片道券 2,800 円<br><br>
                    
                        ＜こども＞<br>
                        ①往復券 4,000 円、片道券 2,200 円<br>②往復券 3,000 円、片道券 1,700 円<br>③往復券 2,500 円、片道券 1,400 円<br><br>
                      </td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>往路<br>
                        ① 9 時〜 15 時 30 分(予定)<br>
                        ② 9 時〜 15 時 30 分(予定)<br>
                        ③ 9 時〜 16 時(予定)<br>
                        <br>
                        復路<br>
                    終演後随時運行</td>
                    </tr>
                  </tbody>
                </table>
              </div>

              <div class="notice-box">
                <h4>注意事項</h4>
                <p class="red no-under">※大人は中学生以上、子どもは小学生となります。</p>
                <p class="red no-under">　未就学児で座席を利用しない場合は無料ですが、座席を利用する場合は子ども料金が適用されます。</p>
                <p>※混雑緩和のため、会場行き（往路）の時間を出発時間帯指定とさせていただきます。</p><p class="red no-under">　（ご購入の際、出発時間帯をお選びいただきご購入ください。）</p><p>
※出発時間帯毎に販売数に限りがございます。販売数終了の場合、他の時間帯や別の発地をご選択ください。<br>
※往復チケット、片道チケット（往路・復路）の販売となりますので、ご希望に合わせてご購入ください。<br>
※ローソン・ミニストップ店頭のLoppiにて販売いたします。（公演前日23:59まで）<br>
※おひとり様1回に付き、4名までの販売となります。<br>
※乗降場所などの詳細情報及びその他注意事項につきましては販売ページにて必ずご確認ください。<br>
※販売時期について：販売期間を1期・2期と分けて行います。</p>
<p class="red no-under">　1期は2期よりもお得になりますので、アクセスについて早期ご購入をご検討ください。</p>
<p>・1期：2月25日（水）19:00～4月26日（日）23:59まで<br>
・2期：4月27日（月）00:00～各公演日前日の23:59まで
</p>
          <div class="ticket-link">
            <a href="https://l-tike.com/concert/mevent/?mid=774334" target="_blank" rel="noopener noreferrer" class="ticket-button">
              シャトルバスのチケット購入はこちら
              <svg class="arrow" width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M1 1L7 7L1 13" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
              </svg>
            </a>
          </div>
              </div>
                            <div class="contact-box">
                <h4>お問い合わせ</h4>
                <p>株式会社JTBビジネストランスフォーム<span>(平日10:00〜17:00)<br></span>
                MAIL：<a href="mailto:event＠jbx.jtb.jp">event＠jbx.jtb.jp</a>　<span>TEL：092-751-9037</span></p>
              </div>
            </div>
          </section>

          <section id="park-ride" class="content-section">
            <h2>パーク&バスライドのご案内</h2>

            <div class="shuttle-route">
              <div class="route-description">
                <p>お車でお越しの際は、以下臨時駐車場（有料）をご利用ください。</p>
                <p>各駐車場から会場直行シャトルバスを運行いたします。</p>
                <p>当日券の販売はございませんので、ご利用の際は必ず事前にチケットをご購入ください。</p>
                <p>なお、各駐車場、混雑緩和のため入庫時間帯を区切っての販売となります。</p>
                <p>時間帯毎に販売数に限りがございますので、予めご了承ください。</p>
              </div>

              <div class="route-diagram">
                <img src="/images/bus-ride.png" alt="パーク&バスライド路線図" />
              </div>

              <div class="route-details">
                <table class="info-table">
                  <tbody>
                    <tr>
                      <th>発車駐車場</th>
                      <td>①戸島ふれあい広場　<span class="sp tab block">②グランメッセ熊本　</span><span class="sp tab">③東京エレクトロン九州</span></td>
                    </tr>
                    <tr>
                      <th>所要時間</th>
                      <td>①約15分　②約20分　③約25分</td>
                    </tr>
                    <tr>
                      <th>料金</th>
                      <td>※1期販売（〜4/26（日）まで）<br>
                        ＜1台あたり＞　9,500 円<br>
                        ※駐車枠1枠＋乗車人数分のバス代含む<br><br>

                    ※2期販売（4/27（月）〜）<br>
                        ＜1台あたり＞　10,000 円<br>                        ※駐車枠1枠＋乗車人数分のバス代含む<br></td>
                    </tr>
                    <tr>
                      <th>運行時間</th>
                      <td>往路<br>
                         9 時〜 16 時<br>
                        <br>
                        復路<br>
                    終演後随時運行</td>
                    </tr>
                  </tbody>
                </table>
              </div>

              <div class="notice-box">
                <h4>注意事項</h4>
                <p>※駐車可能な車種は、軽自動車・小型乗用車・普通自動車に限ります。<br>
※1台に乗車されるすべての方が往復シャトルバスをご利用頂けます。<br>
※混雑緩和のため、駐車場入庫時間帯指定とさせていただきます。<br>
（ご購入の際、駐車場入庫時間帯をお選びいただきご購入ください。）<br>
※入庫時間帯毎に販売数に限りがございます。販売数終了の場合、他の時間帯や別の発地をご選択ください。<br>
※ローソン・ミニストップ店頭のLoppiにて販売いたします。（公演前日23:59まで）<br>
※おひとり様1回に付き、1台までの販売となります。<br>
※駐車場の利用可能時間や乗降場所などの詳細情報及びその他注意事項につきましては販売ページにて必ずご確認ください。<br>
※販売時期について：販売期間を1期・2期と分けて行います。</p>
<p class="red no-under">　1期は2期よりもお得になりますので、アクセスについて早期ご購入をご検討ください。</p><p>
・1期：2月21日（土）12:00～4月26日（日）23:59まで<br>
・2期：4月27日（月）00:00～各公演日前日の23:59まで</p>
          <div class="ticket-link">
            <a href="https://l-tike.com/concert/mevent/?mid=774338" target="_blank" rel="noopener noreferrer" class="ticket-button2">
              パーク&バスライドのチケット購入はこちら
              <svg class="arrow" width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M1 1L7 7L1 13" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
              </svg>
            </a>
          </div>
              </div>
              
                            <div class="contact-box">
                <h4>お問い合わせ</h4>
                <p>株式会社JTBビジネストランスフォーム<span>(平日10:00〜17:00)<br></span>
                MAIL：<a href="mailto:event＠jbx.jtb.jp">event＠jbx.jtb.jp</a>　<span>TEL：092-751-9037</span></p>
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


              <!-- 各エリアの詳細 -->
              <div class="tour-bus-details">
                               <div class="area-detail" data-area="hakata1">

<div class="area-header" @click="toggleArea('hakata1')">
  <h3 class="area-title">「JR 博多駅」①※途中 SA 休憩あり</h3>
  <span class="toggle-icon" :class="{ active: openAreas.hakata1 }">▼</span>
</div>
<div class="area-content" :class="{ open: openAreas.hakata1 }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>博多駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>90 分〜 120 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>9,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>博多駅出発 12 時/会場着 14 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>博多駅着 22 時〜22 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
                
                             <div class="area-detail" data-area="hakata2">

<div class="area-header" @click="toggleArea('hakata2')">
  <h3 class="area-title">「JR 博多駅」②※途中 SA 休憩あり</h3>
  <span class="toggle-icon" :class="{ active: openAreas.hakata2 }">▼</span>
</div>
<div class="area-content" :class="{ open: openAreas.hakata2 }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>博多駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>90 分〜 120 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>9,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>博多駅出発 13 時/会場着 15 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>博多駅着 22 時〜22 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
                
                
                <div class="area-detail">
                  <div class="area-header" @click="toggleArea('kokura')">
                    <h3 class="area-title">「JR 小倉駅」※途中 SA 休憩あり</h3>
                    <span class="toggle-icon" :class="{ active: openAreas.kokura }">▼</span>
                  </div>
                  <div class="area-content" :class="{ open: openAreas.kokura }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>小倉駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>120 分〜 180 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>10,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>小倉駅出発 12 時/会場着 15 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>小倉駅着 22 時 30 分〜23 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>

                <div class="area-detail">
                  <div class="area-header" @click="toggleArea('saga')">
                    <h3 class="area-title">「JR 佐賀駅」※途中 SA 休憩あり</h3>
                    <span class="toggle-icon" :class="{ active: openAreas.saga }">▼</span>
                  </div>
                  <div class="area-content" :class="{ open: openAreas.saga }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>佐賀駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>90 分〜 120 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>9,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>佐賀駅出発 13 時/会場着 15 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>佐賀駅着 22 時〜22 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>

                <div class="area-detail">
                  <div class="area-header" @click="toggleArea('nagasaki')">
                    <h3 class="area-title">「JR ⻑崎駅」※途中 SA 休憩あり</h3>
                    <span class="toggle-icon" :class="{ active: openAreas.nagasaki }">▼</span>
                  </div>
                  <div class="area-content" :class="{ open: openAreas.nagasaki }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>長崎駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>160 分〜 180 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>10,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>長崎駅出発 12 時/会場着 15 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>長崎駅着 22 時 45分〜23 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
                <div class="area-detail">
<div class="area-header" @click="toggleArea('kumamoto1')">
  <h3 class="area-title">「JR 熊本駅」①</h3>
  <span class="toggle-icon" :class="{ active: openAreas.kumamoto1 }">▼</span>
</div>
<div class="area-content" :class="{ open: openAreas.kumamoto1 }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>熊本駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>40 分〜 60 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>6,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>熊本駅出発 11 時/会場着 12 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>熊本駅着 21 時〜21 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
                
                                
                <div class="area-detail">
<div class="area-header" @click="toggleArea('kumamoto2')">
  <h3 class="area-title">「JR 熊本駅」②</h3>
  <span class="toggle-icon" :class="{ active: openAreas.kumamoto2 }">▼</span>
</div>
<div class="area-content" :class="{ open: openAreas.kumamoto2 }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>熊本駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>40 分〜 60 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>6,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>熊本駅出発 14 時/会場着 15 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>熊本駅着 21 時〜21 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
                
                <div class="area-detail">
<div class="area-header" @click="toggleArea('airport1')">
  <h3 class="area-title">「熊本空港」①※往路のみ</h3>
  <span class="toggle-icon" :class="{ active: openAreas.airport1 }">▼</span>
</div>
<div class="area-content" :class="{ open: openAreas.airport1 }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>乗車所</th>
                          <td>熊本空港<br><p class="red no-under">※会場までの往路のみの運行となります。熊本空港への戻り便はございません。</p></td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>20 分〜 40 分</td>
                        </tr>
                        <tr>
                          <th>片道料金(往路のみ)</th>
                          <td>3,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>熊本空港出発 11 時/会場着 11 時 40 分ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td><p class="red no-under">運行無し</p></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
                
                                <div class="area-detail">
<div class="area-header" @click="toggleArea('airport2')">
  <h3 class="area-title">「熊本空港」②※往路のみ</h3>
  <span class="toggle-icon" :class="{ active: openAreas.airport2 }">▼</span>
</div>
<div class="area-content" :class="{ open: openAreas.airport2 }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>乗車所</th>
                          <td>熊本空港<br><p class="red no-under">※会場までの往路のみの運行となります。熊本空港への戻り便はございません。</p></td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>20 分〜 40 分</td>
                        </tr>
                        <tr>
                          <th>片道料金(往路のみ)</th>
                          <td>3,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>熊本空港出発 14 時 45 分/会場着 15 時 25 分ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td><p class="red no-under">運行無し</p></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>
                


                <div class="area-detail">
                  <div class="area-header" @click="toggleArea('oita')">
                    <h3 class="area-title">「JR 大分駅」※途中 SA 休憩あり</h3>
                    <span class="toggle-icon" :class="{ active: openAreas.oita }">▼</span>
                  </div>
                  <div class="area-content" :class="{ open: openAreas.oita }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>大分駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>160 分〜 180 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>10,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>大分駅出発 12 時/会場着 15 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>大分駅着 22 時 30 分〜23 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>

                <div class="area-detail">
                  <div class="area-header" @click="toggleArea('miyazaki')">
                    <h3 class="area-title">「JR 宮崎駅」※途中 SA 休憩あり</h3>
                    <span class="toggle-icon" :class="{ active: openAreas.miyazaki }">▼</span>
                  </div>
                  <div class="area-content" :class="{ open: openAreas.miyazaki }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>宮崎駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>180 分〜 200 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>12,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>宮崎駅出発 12 時/会場着 15 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>宮崎駅着 22 時 30 分〜23 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>

                <div class="area-detail">
                  <div class="area-header" @click="toggleArea('kagoshima')">
                    <h3 class="area-title">「JR 鹿児島中央駅」<span>※途中 SA 休憩あり</span></h3>
                    <span class="toggle-icon" :class="{ active: openAreas.kagoshima }">▼</span>
                  </div>
                  <div class="area-content" :class="{ open: openAreas.kagoshima }">
                    <table class="info-table">
                      <tbody>
                        <tr>
                          <th>発着駅</th>
                          <td>鹿児島中央駅</td>
                        </tr>
                        <tr>
                          <th>所要時間</th>
                          <td>160 分〜 180 分</td>
                        </tr>
                        <tr>
                          <th>料金(往復)</th>
                          <td>10,000 円</td>
                        </tr>
                        <tr>
                          <th>往路運行時間</th>
                          <td>鹿児島中央駅出発 12 時/会場着 15 時ごろ</td>
                        </tr>
                                                <tr>
                          <th>復路運行時間</th>
                          <td>会場出発 20 時〜20 時 45 分<span class="sp"><span class="none">/</span>鹿児島中央駅着 22 時 30 分〜23 時 45 分ごろ</span></td>
                        </tr>
                      </tbody>
                    </table>
                  </div>
                </div>

                
              </div>
                  <div class="notice-box top-margin">
      <h4>注意事項</h4>
      <p>※往復のみでの販売となります。（片道販売はございません。片道不要の場合は権利放棄となります。）</p>
<p class="red no-under">　但し、熊本空港は往路のみの販売となります。</p>
<p>
※ツアーバスの料金は、おとな・こども同額です。（未就学児は座席を利用しない場合のみ無料です）<br>
※最少催行人員に満たない場合、旅行の実施を中止することがございます。<br>
　その場合は、出発日の14日前までにご連絡いたします。<br>
※座席は当日受付順でのご案内となり、混雑時には別グループの方との隣同士のお席や、離れたお席のご案内となる場合がございます。あらかじめご了承ください。<br>
※完全予約制となります。当日の販売はございません。<br>
※受付状況によっては、受付締切前でも満席や運行中止でご予約を承れない場合があります。<br>
※当日は周辺道路の交通渋滞が予想されます。<br>
　バスの運行スケジュールは余裕を持って設定をしておりますが、当日の交通事情、天候等により延着の可能性があります。その際の他交通機関への接続等の保証はございません。<br>
　また、開演時間・最終電車に間に合わない場合でも、ご旅行代金の返金および損害に対する補償はいたしかねますので、あらかじめご了承のうえお申込みください。<br>
※乗降場所、運行時間などの詳細情報及びその他注意事項につきましては後日公開の販売ページにてご案内させていただきます。</p>
          <div class="ticket-link">
            <a href="https://n-tabeat.jtb.co.jp/tabeat/List.aspx?TourNo=b29f271e3e4047988a2cb82a" target="_blank" rel="noopener noreferrer" class="ticket-button3">
                アクセスツアーバスチケット購入はこちら
              <svg class="arrow" width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M1 1L7 7L1 13" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
              </svg>
            </a>
          </div>
    </div>
                            <div class="contact-box">
                <h4>お問い合わせ</h4>
                <p>株式会社JTBビジネストランスフォーム<span>(平日10:00〜17:00)<br></span>
                MAIL：<a href="mailto:event＠jbx.jtb.jp">event＠jbx.jtb.jp</a>　<span>TEL：092-751-9037</span></p>
              </div>
            </div>
          </section>

          <section id="parking" class="content-section">
            <h2>乗降所のご案内</h2>

            <div class="parking-info">
              <div class="parking-map">
                <img src="/images/park-map.png" alt="駐車場マップ" />
              </div>
              <div class="route-description">
                <p>ツアーバス、パーク&バスライド、シャトルバス、タクシーご利用でご来場のお客様の乗降所は上記になります。</p>
              </div>

              <div class="notice-box">
                <h4>注意事項</h4>
                <p>※詳細な注意事項は、決まり次第ご案内させていただきます。</p>
              </div>
            </div>
          </section>
          
          <section id="station" class="content-section">
  <h2>最寄駅から徒歩でのアクセス</h2>

<div class="station-info">
<iframe src="https://www.google.com/maps/embed?pb=!1m28!1m12!1m3!1d41539.61488985665!2d130.77143880464692!3d32.85724673954926!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!4m13!3e2!4m5!1s0x3540f00f592a6c09%3A0xfe697ab655ec99de!2z5YWJ44Gu5qOu6aeF44CB44CSODYxLTgwMDEg54aK5pys55yM54aK5pys5biC5YyX5Yy65q2m6JS144Kx5LiYIOOAkjg2MS04MDAyIDkg5LiB55uu!3m2!1d32.857966399999995!2d130.7867121!4m5!1s0x3540efdfaae84219%3A0xf218b5c8e7f176f6!2z54aK5pys55yM54aK5pys5biC5p2x5Yy65bmz5bGx55S677yS77yX77yX77yWIOeGiuacrOecjOawkee3j-WQiOmBi-WLleWFrOWckumZuOS4iuertuaKgOWgtO-8iOOBiOOBjOOBiuWBpeW6t-OCueOCv-OCuOOCouODoO-8iQ!3m2!1d32.8368628!2d130.8001371!5e0!3m2!1sja!2sjp!4v1767855175732!5m2!1sja!2sjp" width="100%" height="500px" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
    <div class="route-description margin-adjust">
      <p>会場への最寄駅は<strong>光の森駅（JR豊肥本線）</strong>となります。光の森駅から会場までは徒歩50分ほどかかります。<br>交通量が多い道路を横断する場所もございますので、十分ご注意の上ご来場ください。</p>
      <p>  光の森駅の時刻表は
      <a href="https://www.jrkyushu-timetable.jp/cgi-bin/jr-k_time/tt_dep.cgi?c=29563" target="_blank" rel="noopener noreferrer" class="external-link">
こちらから
  <svg class="external-icon" width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
    <path d="M11 7.5V11.5C11 11.7652 10.8946 12.0196 10.7071 12.2071C10.5196 12.3946 10.2652 12.5 10 12.5H2.5C2.23478 12.5 1.98043 12.3946 1.79289 12.2071C1.60536 12.0196 1.5 11.7652 1.5 11.5V4C1.5 3.73478 1.60536 3.48043 1.79289 3.29289C1.98043 3.10536 2.23478 3 2.5 3H6.5M9 1.5H12.5M12.5 1.5V5M12.5 1.5L6 8" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
  </svg>
</a></p>
    </div>

    <div class="station-routes">
    </div>

    <div class="notice-box">
      <h4>注意事項</h4>
      <p>※公演当日は混雑が予想されますので、時間に余裕を持ってお越しください。</p>
      <p>※詳細な徒歩ルートは、上記のアクセスマップをご確認ください。</p>
    </div>
  </div>
</section>

<section id="wheelchair" class="content-section">
  <h2>車いすでのご来場について</h2>

  <div class="wheelchair-info">
    <p class="intro-text">車いすでご来場の方へのご案内です。</p>

    <ul class="wheelchair-list">
      <li>車いす専用の駐車場(有料)をご用意致します。</li>
      <li>一般駐車券の購入は不要です。車いす専用駐車場券(有料)の発売詳細に関しては、決まり次第、当サイトにてご案内いたします。</li>
    </ul>
  </div>
</section>

          <section id="faq" class="content-section">
            <h2>よくある質問</h2>

            <div class="faq-info">
              <p class="intro-text">ご来場に関する主なQ&Aです。お問い合わせの前にご確認ください。</p>

              <div class="faq-list">
                <div class="faq-item">
                  <div class="faq-header" @click="toggleFaq('bicycle')">
                    <p class="question">Q. 自転車、バイク等の駐輪場はありますか？</p>
                    <div class="toggle-icon" :class="{ active: openFaqs.bicycle }">
                      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <line class="horizontal" x1="4" y1="12" x2="20" y2="12" stroke="#333" stroke-width="2" stroke-linecap="round"/>
                        <line class="vertical" x1="12" y1="4" x2="12" y2="20" stroke="#333" stroke-width="2" stroke-linecap="round"/>
                      </svg>
                    </div>
                  </div>
                  <div class="faq-answer" :class="{ open: openFaqs.bicycle }">
                    <p class="answer">A. 駐輪場はございます。詳細については決まり次第当ホームページに記載いたします。
なお、指定の場所以外の駐輪はおやめください。</p>
                  </div>
                </div>

                <div class="faq-item">
                  <div class="faq-header" @click="toggleFaq('pregnancy')">
                    <p class="question">Q. 妊婦なのですが、車いす専用駐車場の利用は可能でしょうか？</p>
                    <div class="toggle-icon" :class="{ active: openFaqs.pregnancy }">
                      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <line class="horizontal" x1="4" y1="12" x2="20" y2="12" stroke="#333" stroke-width="2" stroke-linecap="round"/>
                        <line class="vertical" x1="12" y1="4" x2="12" y2="20" stroke="#333" stroke-width="2" stroke-linecap="round"/>
                      </svg>
                    </div>
                  </div>
                  <div class="faq-answer" :class="{ open: openFaqs.pregnancy }">
                    <p class="answer">A. 可能です。公演のチケットを確保後に、キョードー西日本までお問い合わせください。</p>
                  </div>
                </div>

                <div class="faq-item">
                  <div class="faq-header" @click="toggleFaq('pickup')">
                    <p class="question">Q. 公演当日、送迎は可能でしょうか？</p>
                    <div class="toggle-icon" :class="{ active: openFaqs.pickup }">
                      <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <line class="horizontal" x1="4" y1="12" x2="20" y2="12" stroke="#333" stroke-width="2" stroke-linecap="round"/>
                        <line class="vertical" x1="12" y1="4" x2="12" y2="20" stroke="#333" stroke-width="2" stroke-linecap="round"/>
                      </svg>
                    </div>
                  </div>
                  <div class="faq-answer" :class="{ open: openFaqs.pickup }">
                    <p class="answer">A. 送迎により周辺道路の渋滞が生じ、シャトルバス・ツアーバスの発着に大きな影響を与えますので、送迎でのご来場はおやめください。
なお、公演当日、えがお健康スタジアム周辺は交通規制を行いますので一般車両の乗り入れは行えません。</p>
                  </div>
                </div>
              </div>
            </div>
          </section>
        </div>

        <!-- クロージングセクション -->
        <section class="closing-section">
          <p class="closing-text">
                   <span class="sp">ご来場の皆さまがスムーズにアクセスできるよう、<span class="tab">
     事前のご確認とチケットのご購入をお願いいたします。</span></span>
            <br />
            公演当日は時間に余裕をもって、安全にお越しください。
          </p>
          <div class="official-link">
            <a href="https://backnumber.info/feature/stadiumtour2026" target="_blank" rel="noopener noreferrer" class="official-button">
              back number 熊本公演詳細はこちら
              <svg class="arrow" width="8" height="14" viewBox="0 0 8 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M1 1L7 7L1 13" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
              </svg>
            </a>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const activeSection = ref("notes");
const isTransitioning = ref(false);
const isMenuOpen = ref(false);
const isLoading = ref(true); // 追加


const openAreas = ref({
  hakata1: false,  // hakata → hakata1
  hakata2: false,  // 追加
  kokura: false,
  kumamoto1: false,  // kumamoto → kumamoto1
  kumamoto2: false,  // 追加
  saga: false,
  nagasaki: false,
  airport1: false,  // airport → airport1
  airport2: false,  // 追加
  oita: false,
  miyazaki: false,
  kagoshima: false,
});

const openFaqs = ref({
  bicycle: false,
  pregnancy: false,
  pickup: false
});

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  
  // ナビゲーション要素を取得
  const nav = document.querySelector('.fixed-navigation');
  
  if (isMenuOpen.value) {
    nav.classList.add('mobile-open');
    document.body.style.overflow = 'hidden';
  } else {
    nav.classList.remove('mobile-open');
    document.body.style.overflow = '';
  }
};

const closeMenu = () => {
  isMenuOpen.value = false;
  const nav = document.querySelector('.fixed-navigation');
  nav.classList.remove('mobile-open');
  document.body.style.overflow = '';
};

const toggleFaq = (faq) => {
  Object.keys(openFaqs.value).forEach(key => {
    if (key !== faq) {
      openFaqs.value[key] = false;
    }
  });
  openFaqs.value[faq] = !openFaqs.value[faq];
};

const toggleArea = (area) => {
  openAreas.value[area] = !openAreas.value[area];
};

const handleNavClick = (id) => {
  const overlay = document.querySelector('.loading-overlay');
  
  // fade-outクラスを削除してロゴを表示可能な状態に
  if (overlay) {
    overlay.classList.remove('fade-out');
  }
  
  isLoading.value = true;
  closeMenu();
  
  // ローディングが表示されてからスクロール実行
  setTimeout(() => {
    scrollTo(id);
  }, 300);
};

const scrollTo = async (id) => {
  if (isTransitioning.value) return;

  isTransitioning.value = true;
  const mainContent = document.querySelector(".main-content");
  const overlay = document.querySelector('.loading-overlay');
  const accessPage = document.querySelector('.access-page');

  if (!mainContent) {
    isTransitioning.value = false;
    isLoading.value = false;
    return;
  }

  // メインコンテンツをふわっと消す
  if (accessPage) {
    accessPage.classList.remove('loaded');
  }
  await new Promise((resolve) => setTimeout(resolve, 400));

  const element = document.getElementById(id);
  if (element) {
    const offset = 0;
    const elementPosition = element.getBoundingClientRect().top + window.pageYOffset;
    const offsetPosition = elementPosition - offset;

    window.scrollTo({
      top: offsetPosition,
      behavior: "auto",
    });
  }

  await new Promise((resolve) => setTimeout(resolve, 100));
  activeSection.value = id;

  // fade-outクラスを追加してロゴをふわっと消す
  if (overlay) {
    overlay.classList.add('fade-out');
  }
  
  // ロゴが消えた後、背景を消してメインコンテンツを表示
  setTimeout(() => {
    isLoading.value = false;
    if (accessPage) {
      accessPage.classList.add('loaded');
    }
    // 次回のために fade-out を削除
    if (overlay) {
      overlay.classList.remove('fade-out');
    }
  }, 500);
  
  isTransitioning.value = false;
};

const scrollToTop = async () => {
  if (isTransitioning.value) return;

  isTransitioning.value = true;
  isLoading.value = true;
  closeMenu(); // この行を追加
  
  const overlay = document.querySelector('.loading-overlay');
  const accessPage = document.querySelector('.access-page');

  // メインコンテンツをふわっと消す
  if (accessPage) {
    accessPage.classList.remove('loaded');
  }
  await new Promise((resolve) => setTimeout(resolve, 400));

  window.scrollTo({
    top: 0,
    behavior: "auto",
  });

  await new Promise((resolve) => setTimeout(resolve, 100));
  activeSection.value = "notes";

  // fade-outクラスを追加してロゴをふわっと消す
  if (overlay) {
    overlay.classList.add('fade-out');
  }
  
  // ロゴが消えた後、背景を消してメインコンテンツを表示
  setTimeout(() => {
    isLoading.value = false;
    if (accessPage) {
      accessPage.classList.add('loaded');
    }
    // 次回のために fade-out を削除
    if (overlay) {
      overlay.classList.remove('fade-out');
    }
  }, 500);
  
  isTransitioning.value = false;
};

const updateActiveSection = () => {
  if (isTransitioning.value) return;

  const sections = ["notes", "map", "shuttle", "park-ride", "tour-bus", "parking", "station", "wheelchair", "faq"];
  const windowHeight = window.innerHeight;
  const documentHeight = document.documentElement.scrollHeight;
  const scrollTop = window.pageYOffset || document.documentElement.scrollTop;

  if (scrollTop + windowHeight >= documentHeight - 50) {
    activeSection.value = "faq";
    return;
  }

  for (const sectionId of sections) {
    const element = document.getElementById(sectionId);
    if (element) {
      const rect = element.getBoundingClientRect();
      if (rect.top <= 200 && rect.bottom >= 200) {
        activeSection.value = sectionId;
        break;
      }
    }
  }
};

const setupScrollAnimation = () => {
  const sectionStates = new Map();

  const sectionObserver = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        const id = entry.target.id;
        const wasVisible = sectionStates.get(id) || false;

        if (entry.isIntersecting && !wasVisible) {
          entry.target.classList.add("is-visible");
          sectionStates.set(id, true);
        } else if (!entry.isIntersecting && wasVisible) {
          entry.target.classList.remove("is-visible");
          sectionStates.set(id, false);
        }
      });
    },
    {
      threshold: 0,
      rootMargin: "-180px 0px -180px 0px",
    }
  );

  const sections = document.querySelectorAll(".content-section");
  sections.forEach((section) => {
    sectionStates.set(section.id, false);
    sectionObserver.observe(section);
  });

  const navigation = document.querySelector(".fixed-navigation");
  const notesSection = document.getElementById("notes");

  if (navigation && notesSection) {
    let isNavVisible = false;

    const navObserver = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting && !isNavVisible) {
            navigation.classList.add("is-visible");
            isNavVisible = true;
          } else if (!entry.isIntersecting && isNavVisible) {
            const rect = notesSection.getBoundingClientRect();
            if (rect.top > window.innerHeight / 2) {
              navigation.classList.remove("is-visible");
              isNavVisible = false;
            }
          }
        });
      },
      {
        threshold: 0,
        rootMargin: "-180px 0px -180px 0px",
      }
    );

    navObserver.observe(notesSection);
  }
};

onMounted(() => {
    
      window.scrollTo(0, 0);
  window.addEventListener("scroll", updateActiveSection);
  window.addEventListener("resize", handleResize);
  updateActiveSection();

  // 画像の読み込みを待つ
  const logoImg = document.querySelector('.loading-logo');
  if (logoImg && !logoImg.complete) {
    logoImg.onload = () => {
      startPageLoad();
    };
  } else {
    startPageLoad();
  }
});

const startPageLoad = () => {
  setTimeout(() => {
    setupScrollAnimation();

    const navigation = document.querySelector(".fixed-navigation");
    const notesSection = document.getElementById("notes");
    const sections = document.querySelectorAll(".content-section");

    if (notesSection) {
      const rect = notesSection.getBoundingClientRect();
      if (rect.top < window.innerHeight - 150) {
        if (navigation) {
          navigation.classList.add("is-visible");
        }
      }
    }

    sections.forEach((section) => {
      const rect = section.getBoundingClientRect();
      if (rect.top < window.innerHeight - 100 && rect.bottom > 150) {
        section.classList.add("is-visible");
      }
    });
    
    // ページ読み込み完了後、ローディングを非表示
    setTimeout(() => {
      const overlay = document.querySelector('.loading-overlay');
      const accessPage = document.querySelector('.access-page');
      
      // fade-outクラスを追加してロゴをふわっと消す
      if (overlay) {
        overlay.classList.add('fade-out');
      }
      
      // ロゴが消えた後、背景を消してメインコンテンツを表示
      setTimeout(() => {
        isLoading.value = false;
        if (accessPage) {
          accessPage.classList.add('loaded');
        }
      }, 500);
    }, 300);
  }, 100);
};

const handleResize = () => {
  if (window.innerWidth > 860 && isMenuOpen.value) {
    const navigation = document.querySelector(".fixed-navigation");
    
    // メニューを閉じる
    closeMenu();
    
    // PC表示に戻った時は常にナビゲーションを表示
    if (navigation) {
      // 一時的にトランジションを無効化
      navigation.style.transition = 'none';
      navigation.classList.add("is-visible");
      
      // 次のフレームでトランジションを再度有効化
      requestAnimationFrame(() => {
        navigation.style.transition = '';
      });
    }
  }
};

onUnmounted(() => {
  window.removeEventListener("scroll", updateActiveSection);
  window.removeEventListener("resize", handleResize); // この行を追加
  document.body.style.overflow = '';
});

</script>

<style scoped>
.access-page {
  width: 100%;
  min-height: 100vh;
  background: url("/images/main-background.jpg") no-repeat center center;
  background-attachment: fixed;
  background-size: cover;
  font-family: "noto-sans-cjk-jp", sans-serif;
  font-weight: 400;
  font-style: normal;
}

.loading-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #ffffff;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 9999;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.6s ease;
}

.loading-overlay.active {
  opacity: 1;
  pointer-events: auto;
}

.loading-logo {
  width: 100%;
  max-width: 300px;
  height: auto;
  opacity: 0;
  transform: scale(0.95);
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.loading-overlay.active .loading-logo {
  opacity: 1;
  transform: scale(1);
}

.loading-overlay.fade-out .loading-logo {
  opacity: 0;
  transform: scale(0.95);
}

@keyframes fadeInOut {
  0% {
    opacity: 0;
    transform: scale(0.9);
  }
  50% {
    opacity: 1;
    transform: scale(1);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

@media (max-width: 480px) {
  .loading-logo {
    max-width: 200px;
  }
}

/* メインコンテンツの初期状態 */
.access-page > *:not(.loading-overlay):not(.hamburger-button):not(.mobile-menu-overlay) {
  opacity: 0;
  transition: opacity 0.8s ease 0.3s;
}

.access-page.loaded > *:not(.loading-overlay):not(.hamburger-button):not(.mobile-menu-overlay) {
  opacity: 1;
}

/* ハンバーガーメニューボタン */
.hamburger-button {
  display: none;
  position: fixed;
  top: 5px;
  right: 10px; /* left: 20px; から変更 */
  z-index: 2000;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: #000;
  border: none;
  cursor: pointer;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 6px;
  padding: 0;
  transition: background 0.3s;
}


.hamburger-button span {
  display: block;
  width: 25px;
  height: 2px;
  background: #fff;
  transition: all 0.3s;
}

.hamburger-button.active span:nth-child(1) {
  transform: translateY(8px) rotate(45deg);
}

.hamburger-button.active span:nth-child(2) {
  opacity: 0;
  transform: scale(0);
}

.hamburger-button.active span:nth-child(3) {
  transform: translateY(-8px) rotate(-45deg);
}

/* モバイルメニューオーバーレイ */
.mobile-menu-overlay {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  z-index: 1500;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s;
}

.mobile-menu-overlay.active {
  opacity: 1;
  pointer-events: auto;
}

.hero-section {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
  height: min(100vh, 800px); /* この書き方の方が明確 */
  display: flex;
  flex-direction: column;
  justify-content: center;
}

/* descriptionはhero-sectionの外なので、通常のセクションとして */
.description {
  max-width: 1280px;
  margin: 0 auto;
  padding: 40px 20px 60px;
  text-align: center;
}

.main-visual {
  width: 100%;
  text-align: center;
  padding: 0 0 40px;
}
.main-visual img {
  max-width: clamp(150px, 50vh, 400px);
  width: 100%;
  height: auto;
}
.event-info {
  text-align: center;
  line-height: 1;
}

.event-date {
  font-size: 36px;
  font-weight: bold;
  letter-spacing: 2px;
}

.day {
  font-size: 23px;
  margin-left: 5px;
}

.event-time {
  font-size: 24px;
  font-weight: bold;
  margin: 15px 0 20px;
  color: #333;
}

.small {
  font-size: 16px;
}

.venue-name {
  font-size: 36px;
  font-weight: bold;
  letter-spacing: 1px;
  margin-bottom: 20px;
}

.page-title {
  font-size: 32px;
  font-weight: bold;
  letter-spacing: 0.1em;
}


.description p {
  line-height: 1.8;
  color: #333;
  font-size: 16px;
}

.content-wrapper {
  position: relative;
  max-width: 1280px;
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
  background: #000; /* #fff から #333 に変更 */
  border-radius: 16px;
  padding: 20px 0 20px 20px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  opacity: 0;
  transition: opacity 0.8s ease;
  pointer-events: auto;
}

.fixed-navigation.is-visible {
  opacity: 1;
}

.nav-logo {
  background: #000; /* #333 から #000 に変更（より濃い黒） */
  margin: -20px 0px 10px -20px;
  padding: 10px 20px;
  border-radius: 16px 16px 0 0;
}

.nav-logo {
  background: #000;
  margin: -20px 0px 10px -20px;
  padding: 20px 20px 10px;
  border-radius: 16px 16px 0 0;
  text-align: center; /* 画像を中央揃え */
}

.nav-logo-image {
  width: 100%;
  max-width: 120px; /* 適切なサイズに調整 */
  height: auto;
  display: block;
  margin: 0 auto;
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
  left: -16px;
  top: 50%;
  transform: translateY(-50%);
  opacity: 0;
  transition: opacity 0.3s;
  color: #fff; /* #333 から #fff に変更 */
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
  color: #fff; /* #333 から #fff に変更 */
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
  padding: 80px 40px;
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
  content: "〇";
  position: absolute;
  left: 0;
}

.notes-list li:last-child {
  margin-bottom: 0;
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
    margin-top: 50px;
  margin-bottom: 30px;
  line-height: 1.8;
  text-align: left;
}

.route-description p {
  margin-bottom: 12px;
}

.route-diagram {
  width: 100%;
  text-align: center;
  margin: 50px 0;
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

.area-detail {
  margin-bottom: 40px;
  overflow: hidden;
}



.area-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #333;
  cursor: pointer;
  transition: background 0.3s;
}

.area-title {
  font-size: 20px;
  font-weight: bold;
  margin: 0;
  padding: 0;
  border: none;

}

.toggle-icon {
  font-size: 20px;
  transition: transform 0.3s;
  color: #666;
}

.toggle-icon.active {
  transform: rotate(180deg);
}

.area-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease-in-out;
}

.area-content > table {
  padding: 20px 0;
  margin-top: 10px;
}

.area-content.open {
  max-height: 700px;
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

.parking-fee {
  margin: 40px 0;
}

.parking-map {
  margin: 40px 0;
  border-radius: 8px;
  text-align: center;
}

.parking-map img {
  width: 100%;
  height: auto;
  display: block;
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

.wheelchair-list li:last-child {
  margin-bottom: 0;
}

.wheelchair-list li {
  margin-bottom: 20px;
  padding-left: 1.5em;
  position: relative;
  line-height: 1.8;
  color: #333;
  font-size: 16px;
}

.wheelchair-list li:before {
  content: "〇";
  position: absolute;
  left: 0;
}

.wheelchair-list li:last-child {
  margin-bottom: 0;
}


.area-detail:last-child {
  margin-bottom: 0;
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
  margin-bottom: 20px;
  overflow: hidden;
}

.faq-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  border: 1px solid #ddd;
  cursor: pointer;
  transition: background 0.3s;
}

.faq-header:hover {
  background: #f8f8f8;
}

.question {
  font-size: 16px;
  font-weight: bold;
  line-height: 1.8;
  margin: 0;
  color: #333;
  flex: 1;
}

.toggle-icon {
  width: 24px;
  height: 24px;
  flex-shrink: 0;
}

.toggle-icon svg {
  display: block;
}

.toggle-icon .vertical {
  transition: opacity 0.3s ease, transform 0.3s ease;
  transform-origin: center;
}

.toggle-icon.active .vertical {
  opacity: 0;
  transform: rotate(90deg);
}

.faq-answer {
  max-height: 0;
  opacity: 0;
  transition: max-height 0.2s ease-in-out, opacity 0.2s ease-in-out;
  overflow: hidden;
  background: #333;
}

.faq-answer.open {
  max-height: 500px;
  opacity: 1;
}

.faq-answer > .answer {
  padding: 20px;
  margin: 0;
  color: #fff;
  line-height: 1.8;
}

.answer {
  font-size: 16px;
}

.faq-item:last-child {
  margin-bottom: 0;
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
  gap: 15px;
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

.ticket-link {
  display: flex;
  justify-content: flex-start;
}

.ticket-button {
  display: inline-flex;
  align-items: center;
  padding: 15px 52px 15px 30px;
  background: #000;
  color: #fff;
  text-decoration: none;
  font-size: 16px;
  font-weight: bold;
  border-radius: 50px;
  transition: opacity 0.3s;
  margin-top:25px;
  position: relative;
}

.ticket-button2 {
  display: inline-flex;
  align-items: center;
  padding: 15px 52px 15px 30px;
  background: #000;
  color: #fff;
  text-decoration: none;
  font-size: 16px;
  font-weight: bold;
  border-radius: 50px;
  transition: opacity 0.3s;
  margin-top:25px;
  position: relative;
}

.ticket-button3 {
  display: inline-flex;
  align-items: center;
  padding: 15px 52px 15px 30px;
  background: #000;
  color: #fff;
  text-decoration: none;
  font-size: 16px;
  font-weight: bold;
  border-radius: 50px;
  transition: opacity 0.3s;
  margin-top:25px;
  position: relative;
}

.ticket-button:hover {
  opacity: 0.8;
}

.ticket-button .arrow {
  position: absolute;
  top:21px;
  right:30px;
  width: 8px;
  height: 14px;
  flex-shrink: 0;
}



.space{
    display: none;
}

.contact-box {
  margin-top: 30px;

}

.contact-box h4 {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 10px;
}

.contact-box p {
  margin: 0;
  line-height: 1.6;
}

.contact-box a {
  text-decoration: none;
}

.contact-box a:hover {
  opacity: 0.7;
}


@media (max-width: 480px) {
  
  .contact-box h4 {
    font-size: 16px;
  }
  
  .contact-box p {
    font-size: 14px;
    span{
        display: block;
    }
  }
}

/* ===============================================
   レスポンシブデザイン
   =============================================== */
@media (min-width: 861px) and (max-width: 1100px) {
   .block{
    display: block;
}
}

@media (min-width: 861px) and (max-width: 1050px) {
   .step{
    display: block;
}
}

   
   
/* タブレット - 860px以下 */
@media (max-width: 860px) {
  /* ハンバーガーメニューボタンを表示 */
  .hamburger-button {
    display: flex;
  }

  /* モバイルメニューオーバーレイを有効化 */
  .mobile-menu-overlay {
    display: block;
  }

  /* サイドナビゲーションをモバイルメニューに変更 */
  .content-wrapper {
    padding: 0 20px;
  }

  .notes-with-nav {
    position: fixed;
    right: 0; /* 右端基準 */
    left: auto; /* leftの指定を無効化 */
    top: 0;
    width: 280px;
    height: 100vh;
    pointer-events: auto;
    z-index: 1600;
    transform: translateX(100%); /* 右に100%移動して隠す */
    transition: transform 0.3s ease;
  }

  /* メニューが開いたときだけ表示 */
  .notes-with-nav:has(.mobile-open) {
    transform: translateX(0); /* 元の位置に戻す */
  }

  .fixed-navigation {
    position: static;
    width: 100%;
    height: 100%;
    border-radius: 0;
    opacity: 1;
    overflow-y: auto;
    padding: 80px 20px 20px;
    margin-left: 0; /* これを追加 */
  }

  .nav-logo {
    margin: -80px -20px 20px -20px;
    border-radius: 0;
    padding: 20px;
  }

  .nav-menu {
    padding-left: 0;
  }

  .nav-menu li {
    padding-left: 20px;
  }

  .nav-menu li::before {
    left: 0;
  }

  .nav-menu a {
    font-size: 16px;
    padding: 15px 0;
  }

  /* メインコンテンツの調整 */
  .main-content {
    max-width: 100%;
  }

  .content-section {
    padding: 60px 20px;
  }

  .content-section h2 {
    font-size: 28px;
    margin-bottom: 40px;
  }
}

@media (min-width: 481px) and (max-width: 860px) {
  .tab{
    display: block;
  }
  
    .nav-logo {
    margin: -80px -20px 20px -20px;
    border-radius: 0;
    padding: 40px 20px 20px;
    text-align: center;
  }

  .nav-logo-image {
    max-width: 160px; /* タブレット用のサイズ */
    margin: 0 auto;
  }
}


/* スマホ - 480px以下 */
@media (max-width: 480px) {
  /* ヒーローセクション */
.hero-section {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
  height: min(100vh, 800px); /* この書き方の方が明確 */
  display: flex;
  flex-direction: column;
  justify-content: center;
}

  .description {
    padding: 30px 15px 40px;
  }

  .main-visual {
    padding: 0 0 30px;
  }

  .main-visual img {
    max-width: 350px;
  }

  .event-date {
    font-size: 24px;
  }

  .day {
    font-size: 14px;
    margin-left: 5px;
  }

  .event-time {
    font-size: 16px;
    margin: 15px 0 20px;
  }

  .small {
    font-size: 14px;
  }

  .venue-name {
    font-size: 24px;
  }

  .page-title {
    font-size: 20px;
  }

   .nav-logo {
    position: absolute;
    top: 0;
    left: 0;
    margin: 0;
    border-radius: 0;
    padding: 20px;
    width: 100%;
    text-align: center;
  }

  .nav-logo-image {
    max-width: 150px; /* スマホではやや大きめ */
  }

  .description p {
    font-size: 14px;
      text-align: left;
  }


  /* コンテンツセクション */
  .content-section {
    padding: 40px 15px;
  }

  .content-section h2 {
    font-size: 22px;
    margin-bottom: 30px;
  }

  .content-section .section-intro {
    font-size: 16px;
  }
  
  .sp{
    display: block;
  }
  .none{
    display: none;
  }

  .space{
    display: inline;
  }
  .notes-list {
    padding: 15px 0 0 0;
  }

  .notes-list li {
    font-size: 14px;
    padding-left: 20px;
  }
  
  /* 最後の項目のマージンを削除 */
.notes-list li:last-child {
  margin-bottom: 0;
}

  /* テーブル */
  .info-table th,
  .info-table td {
    display: block;
    width: 100%;
    padding: 10px 0;
  }

  .info-table th {
    font-size: 14px;
    padding-bottom: 5px;
    border-bottom: none; 
  }

  .info-table td {
    font-size: 14px;
    padding-top: 10px;
    padding-bottom: 10px;
    border-top: 1px solid #ccc;
    border-bottom: 1px solid #ccc; 
  }

  .info-table tr {
    display: block;
    margin-bottom: 10px;
  }
  
.info-table tr:last-child td {
  border-bottom: 1px solid #ccc !important;
}
  
    .info-table tr:last-child {
    margin-bottom: 20px;
  }
  
  .toggle-icon {
  font-size: 20px;
  transition: transform 0.3s;
  color: #666;
  transform: translateY(-7px); 
}


.sp-none{
 display: none;   
}

.toggle-icon.active {
  transform: translateY(7px) rotate(180deg);
}

  /* 地図 */
  .map-container iframe {
    height: 300px;
  }

  /* FAQ */
  .faq-header {
    padding: 15px;
  }

  .question {
    font-size: 14px;
  }

  .toggle-icon {
    width: 20px;
    height: 20px;
  }

  .answer {
    font-size: 14px;
  }

  /* クロージング */
  .closing-section {
    padding: 30px 15px 60px;
  }

  .closing-text {
    font-size: 14px;
    text-align: left;
  }

  .official-button {
    font-size: 14px;
    padding: 15px 20px;
    white-space: nowrap;
    line-height: 1;
  }
  
  
  .ticket-button {
  display: inline-flex;
  align-items: center;
  padding: 15px 20px;
  background: #000;
  color: #fff;
  font-size: 14px;
  line-height: 1;
  border-radius: 50px;
  transition: opacity 0.3s;
  margin-top:26px;
  white-space: nowrap;
  position: relative;
  width: 100%;
}

  .ticket-button2 {
  display: inline-flex;
  align-items: center;
  padding: 16px 20px;
  background: #000;
  color: #fff;
  font-size: 12px;
  line-height: 1;
  border-radius: 50px;
  transition: opacity 0.3s;
  margin-top:26px;
  white-space: nowrap;
  position: relative;
  width: 100%;
}

  .ticket-button3 {
  display: inline-flex;
  align-items: center;
  padding: 15.5px 20px;
  background: #000;
  color: #fff;
  font-size: 13px;
  line-height: 1;
  border-radius: 50px;
  transition: opacity 0.3s;
  margin-top:26px;
  white-space: nowrap;
  position: relative;
  width: 100%;
}



.ticket-button .arrow {
    position: absolute;
    right:20px;
    top:16px;
  width: 8px;
  height: 13px;
  flex-shrink: 0;
}


.ticket-button2 .arrow {
    position: absolute;
    right:20px;
    top:16px;
  width: 8px;
  height: 13px;
  flex-shrink: 0;
}


.ticket-button3 .arrow {
    position: absolute;
    right:20px;
    top:17px;
  width: 8px;
  height: 13px;
  flex-shrink: 0;
}


  /* ハンバーガーボタン */
  .hamburger-button {
    width: 45px;
    height: 45px;
    top: 10px;
    right: 10px;
  }
  .hamburger-button span {
    width: 22px;
  }

  /* モバイルナビゲーション - スマホは全面表示 */
  .notes-with-nav {
    width: 100%; /* 250px から 100% に変更 */
  }
  
  .nav-logo {
    position: absolute;
    top: 0;
    left: 0;
    margin: 0;
    border-radius: 0;
    padding: 35px 20px;
    width: 100%; /* auto から 100% に変更 */
  }

  .nav-menu {
    padding-left: 0;
    text-align: center; /* 中央揃え */
    margin-top: 95px; /* ロゴの下にスペース */
  }
  
  .nav-menu a {
    padding: 16px 0;
  }

  .nav-menu li {
    padding-left: 0; /* 20px から 0 に変更 */
  }

  .nav-menu li::before {
    display: none; /* ・を非表示 */
  }
  
    .route-description  {
    margin-bottom: 20px;
    margin-top: 30px;
  }
  
  .route-description p {
    font-size: 14px;
  }
  
  .route-diagram{
    margin:25px 0 ;
  }
  
  .notice-box h4{
    font-size: 16px;
  }
  
    .notice-box p{
    font-size: 14px;
  }
  
  .area-title{
    font-size: 16px;
    span{
       font-size: 14px;
    }
  }
  
  .tour-bus-details{
    margin-top: 30px;
  }
  
  .route-details{
    padding: 0 ;
  }
  
  .parking-map{
    margin:30px 0;
  }
  
  .intro-text{
    font-size: 14px !important;
  }
  
  .wheelchair-list li{
    font-size: 14px;
  }
  
  .faq-header {
    padding: 15px;
    align-items: center; /* 中央揃え */
  }

  .question {
    font-size: 14px;
  }
  
  .toggle-icon svg {
        width: 20px;
    height: 20px;
    transform: translateY(6px);
  }
  
  .toggle-icon.active svg {
  transform: translateY(6px); /* activeの時はさらに上に */
}

  .station-info iframe {
    height: 370px; /* 500px → 350px に縮小 */
  }
  
  .access-diagram {
  margin: 30px auto 0;
}

.margin-adjust{
    margin-top: 20px !important;
}

}

.top-margin{
    margin-top: 30px;
}

.red{
    color: red !important;
    text-decoration: underline;
}

.external-link {
  color: #1976d2;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 4px;
}

.external-link:hover {
  opacity: 0.7;
}

.external-icon {
  flex-shrink: 0;
}

.no-under{
    text-decoration: none;
}


</style>
