---
description: jdk8u292 버전 기준으로 공통적으로 설정해놓으면 좋은 jvm option 을 간추려 보자.
---

# 최소한 설정해놓으면 좋은 jvm option

### jvm option 후보들

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xC635;&#xC158; &#xBA85;</th>
      <th style="text-align:left">&#xC635;&#xC158; &#xC758;</th>
      <th style="text-align:left">&#xBE44;&#xACE0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">-XX:+UseG1GC</td>
      <td style="text-align:left">
        <p>g1gc &#xB97C; &#xC0AC;&#xC6A9;&#xD55C;&#xB2E4;.</p>
        <p>4G &#xC774;&#xC0C1;&#xC758; &#xD070; &#xD799;&#xBA54;&#xBAA8;&#xB9AC;&#xB97C;
          &#xAC00;&#xC9C4; &#xACBD;&#xC6B0; &#xC798; &#xC9C0;&#xC6D0;&#xB418;&#xB3C4;&#xB85D;
          &#xD588;&#xB2E4;&#xACE0; &#xD568;.</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-Xms</td>
      <td style="text-align:left">jvm &#xCD5C;&#xC18C; &#xD799;&#xC0AC;&#xC774;&#xC988;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-Xmx</td>
      <td style="text-align:left">jvm &#xCD5C;&#xB300; &#xD799;&#xC0AC;&#xC774;&#xC988;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:NewRatio</td>
      <td style="text-align:left">new/old &#xC601;&#xC5ED; &#xBE44;&#xC728;&#xC744; &#xC815;&#xD55C;&#xB2E4;.</td>
      <td
      style="text-align:left">&#xB9AC;&#xC11C;&#xCE58;</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:SurvivorRatio</td>
      <td style="text-align:left">
        <p>new &#xC601;&#xC5ED;&#xC758; eden, survivor &#xC601;&#xC5ED; &#xBE44;&#xC728;&#xC744;
          &#xC815;&#xD55C;&#xB2E4;.</p>
        <p>&#xB514;&#xD3F4;&#xD2B8; &#xAC12;&#xC740; 8.</p>
      </td>
      <td style="text-align:left">&#xB9AC;&#xC11C;&#xCE58;</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:MetaspaceSize</td>
      <td style="text-align:left">
        <p>&#xD074;&#xB798;&#xC2A4; &#xBA54;&#xD0C0; &#xB370;&#xC774;&#xD130;&#xB97C;
          &#xC800;&#xC7A5;&#xD558;&#xB294; &#xACF5;&#xAC04;&#xC758; &#xC0AC;&#xC774;&#xC988;&#xB97C;
          &#xC9C0;&#xC815;</p>
        <p>java8 &#xBD80;&#xD130; germ &#xC601;&#xC5ED; -&gt; metaspace &#xC601;&#xC5ED;&#xC73C;&#xB85C;
          &#xB300;&#xCCB4;&#xB428;</p>
        <p>native memory &#xC601;&#xC5ED;&#xC5D0; &#xB370;&#xC774;&#xD130;&#xAC00;
          &#xD560;&#xB2F9;&#xB428;.</p>
      </td>
      <td style="text-align:left">&#xB9AC;&#xC11C;&#xCE58;</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:MaxMetaspaceSize</td>
      <td style="text-align:left">
        <p>Metaspace &#xC601;&#xC5ED;&#xC740; &#xCD5C;&#xB300; &#xD55C;&#xACC4;&#xCE58;&#xAC00;
          &#xC9C0;&#xC815;&#xB418;&#xC5B4; &#xC788;&#xC9C0; &#xC54A;&#xC74C;.</p>
        <p>&#xADF8;&#xB807;&#xAE30; &#xB54C;&#xBB38;&#xC5D0; &#xBA54;&#xBAA8;&#xB9AC;&#xB97C;
          &#xB9CE;&#xC774; &#xCC28;&#xC9C0;&#xD558;&#xAC8C; &#xB420; &#xACBD;&#xC6B0;
          &#xC11C;&#xBC84; &#xBD80;&#xD558; &#xC704;&#xD5D8;&#xC774; &#xC788;&#xB2E4;.</p>
      </td>
      <td style="text-align:left">&#xB9AC;&#xC11C;</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+UseGCLogFileRotation</td>
      <td style="text-align:left">gc &#xB85C;&#xADF8;&#xB97C; &#xB85C;&#xD14C;&#xC774;&#xC158; &#xD560;
        &#xC9C0; &#xC5EC;&#xBD80;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:NumberOfGCLogFiles</td>
      <td style="text-align:left">
        <p>&#xB85C;&#xADF8; &#xD30C;&#xC77C;&#xC758; &#xCD5C;&#xB300; &#xAC1C;&#xC218;&#xB97C;
          &#xC9C0;&#xC815;&#xD558;&#xB294; &#xC635;&#xC158;.</p>
        <p>&#xB85C;&#xADF8; &#xC21C;&#xD658; &#xC2DC; &#xC0AC;&#xC6A9;&#xD560; &#xD30C;&#xC77C;
          &#xC218;&#xB97C; &#xC124;&#xC815;&#xD558;&#xBA70; &#xAC12;&#xC740; 1&#xBCF4;&#xB2E4;
          &#xD06C;&#xAC70;&#xB098; &#xAC19;&#xC544;&#xC57C;&#xD568;</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:GCLogFileSize</td>
      <td style="text-align:left">&#xB85C;&#xADF8; &#xC21C;&#xD658; &#xC2DC; &#xB85C;&#xADF8; &#xD30C;&#xC77C;&#xC758;
        &#xD06C;&#xAE30;&#xB97C; &#xC9C0;&#xC815;. &#xAC12;&#xC740; &#xCD5C;&#xC18C;
        8K &#xC774;&#xC0C1;&#xC774;&#xC5EC;&#xC57C;&#xD568;.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-Xloggc</td>
      <td style="text-align:left">GC &#xB294; &#xAE30;&#xBCF8;&#xC801;&#xC73C;&#xB85C; &#xB85C;&#xADF8;&#xB97C;
        stdout &#xC73C;&#xB85C; &#xCD9C;&#xB825;.
        <br />&#xD574;&#xB2F9; &#xC635;&#xC158;&#xC73C;&#xB85C; &#xD30C;&#xC77C;&#xC704;&#xCE58;&#xB97C;
        &#xC9C0;&#xC815;&#xD558;&#xC5EC; &#xD30C;&#xC77C;&#xC5D0; &#xAE30;&#xB85D;&#xD560;
        &#xC218; &#xC788;&#xB2E4;.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintGCDetails</td>
      <td style="text-align:left">
        <p>&#xC0C1;&#xC138;&#xD55C; gc &#xB85C;&#xAE45; &#xBAA8;&#xB4DC;&#xB97C;
          &#xD65C;&#xC131;&#xD654;.</p>
        <p>&#xAC00;&#xBE44;&#xC9C0; &#xCEEC;&#xB809;&#xD130;&#xC758; &#xC885;&#xB958;&#xC5D0;
          &#xB530;&#xB77C; &#xC0C1;&#xC138; &#xC815;&#xBCF4;&#xB4E4;&#xC774; &#xB85C;&#xAE45;&#xB41C;&#xB2E4;.</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintGCTimeStamps</td>
      <td style="text-align:left">JVM &#xC2DC;&#xC791; &#xC774;&#xD6C4; &#xCD08;&#xB2E8;&#xC704;&#xB85C;
        &#xD750;&#xB978; &#xC2E4;&#xC81C; &#xC2DC;&#xAC04;&#xC744; &#xB9E4; &#xB77C;&#xC778;
        &#xBC18;&#xC601;.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintGCDateStamps</td>
      <td style="text-align:left">&#xB9E4; &#xB85C;&#xADF8; &#xB77C;&#xC778;&#xC5D0; &#xC808;&#xB300; &#xB0A0;&#xC9DC;/&#xC2DC;&#xAC04;&#xC744;
        &#xBC18;&#xC601;.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintHeapAtGC</td>
      <td style="text-align:left">
        <p>GC &#xBC1C;&#xC0DD; &#xC804;&#xD6C4;&#xC758; Heap&#xC5D0; &#xB300;&#xD55C;
          &#xC815;&#xBCF4;&#xB97C; &#xC0C1;&#xC138; &#xAE30;&#xB85D;.</p>
        <p>&#xB2E8;&#xC810;&#xC73C;&#xB85C; &#xC624;&#xB79C; &#xAE30;&#xAC04; &#xC2E4;&#xD589;&#xB41C;
          &#xC571;&#xC758; &#xACBD;&#xC6B0; &#xB9CE;&#xC740; &#xBA54;&#xBAA8;&#xB9AC;&#xB97C;
          &#xC0AC;&#xC6A9;&#xD560; &#xC218; &#xC788;&#xB2E4;.</p>
      </td>
      <td style="text-align:left">&#xC120;&#xD0DD;&#xC0AC;</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintClassHistogramAfterFullGC</td>
      <td style="text-align:left">fgc &#xB41C; &#xD6C4;&#xC758; &#xBA54;&#xBAA8;&#xB9AC; &#xC815;&#xBCF4;&#xB97C;
        &#xB85C;&#xADF8;&#xC5D0; &#xAE30;&#xB85D;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintClassHistogramBeforeFullGC</td>
      <td style="text-align:left">fgc &#xB418;&#xAE30; &#xC804; &#xBA54;&#xBAA8;&#xB9AC; &#xC815;&#xBCF4;&#xB97C;
        &#xB85C;&#xADF8;&#xC5D0; &#xAE30;&#xB85D;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+HeapDumpOnOutOfmemoryError</td>
      <td style="text-align:left">oome &#xC5D0;&#xB7EC; &#xBC1C;&#xC0DD; &#xC2DC; &#xD799;&#xB364;&#xD504;
        &#xD30C;&#xC77C;&#xC744; &#xC0DD;&#xC131;&#xD55C;&#xB2E4;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:HeapDumpPath</td>
      <td style="text-align:left">&#xD799;&#xB364;&#xD504; &#xD30C;&#xC77C;&#xC758; &#xC704;&#xCE58;&#xB97C;
        &#xC9C0;&#xC815;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+UseStringDeduplication</td>
      <td style="text-align:left">
        <p>&#xC911;&#xBCF5;&#xB41C; &#xBB38;&#xC790;&#xB97C; gc &#xC2E4;&#xD589;
          &#xC2DC;&#xC5D0; &#xC81C;&#xAC70;&#xD55C;&#xB2E4;.</p>
        <p>java 8 u 20 &#xC774;&#xC0C1;&#xC774;&#xBA70;, g1gc &#xB97C; &#xC0AC;&#xC6A9;&#xD558;&#xB294;
          &#xACBD;&#xC6B0; &#xC0AC;&#xC6A9; &#xAC00;&#xB2A5;.</p>
      </td>
      <td style="text-align:left">&#xC120;&#xD0DD;&#xC0AC;&#xD56D;</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:StringDeduplicationAgeThreshold</td>
      <td style="text-align:left">
        <p>&#xC704; &#xC635;&#xC158; &#xC0AC;&#xC6A9; &#xC2DC; &#xC0AC;&#xC6A9;&#xB418;&#xBA70;,
          gc &#xC2E4;&#xD589; &#xC2DC; &#xC911;&#xBCF5; &#xBB38;&#xC790;&#xB97C;
          &#xC81C;&#xAC70;&#xD560;&#xB54C;</p>
        <p>gc &#xC5D0;&#xC11C; 3&#xD68C; &#xC774;&#xC0C1; &#xC0B4;&#xC544;&#xB0A8;&#xC740;
          &#xAC1D;&#xCCB4;&#xC5D0; &#xB300;&#xD574;&#xC11C;&#xB9CC; &#xC2E4;&#xD589;&#xD55C;&#xB2E4;.</p>
        <p>&#xBA87;&#xD68C; &#xC774;&#xC0C1; &#xC0B4;&#xC544;&#xB0A8;&#xC740; &#xAC1D;&#xCCB4;&#xC5D0;
          &#xB300;&#xD574; &#xC2E4;&#xD589;&#xD560;&#xC9C0; &#xC9C0;&#xC815; &#xAC00;&#xB2A5;.</p>
      </td>
      <td style="text-align:left">&#xC120;&#xD0DD;&#xC0AC;&#xD56D;</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintStringDeduplicationStatistics</td>
      <td style="text-align:left">
        <p>StringDeduplication &#xC2E4;&#xD589;&#xC5D0; &#xB300;&#xD55C; &#xC815;&#xBCF4;&#xB97C;
          &#xD655;&#xC778;&#xD558;&#xACE0; &#xC2F6;&#xC73C;&#xBA74;</p>
        <p>&#xD574;&#xB2F9; &#xC635;&#xC158;&#xC744; &#xC124;&#xC815;.</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:MaxRAMPercentage</td>
      <td style="text-align:left">
        <p>&#xCEE8;&#xD14C;&#xC774;&#xB108;&#xC758; &#xC124;&#xC815;&#xB41C; &#xBA54;&#xBAA8;&#xB9AC;
          &#xAE30;&#xC900; &#xCD5C;&#xB300; &#xD799; &#xD06C;&#xAE30;&#xB97C; &#xC124;&#xC815;.
          <br
          />0.0 ~ 100.0 &#xC73C;&#xB85C; &#xC138;&#xD305;. &#xAE30;&#xBCF8; &#xAC12;
          25.0.
          <br />75.0 &#xC774; &#xC801;&#xB2F9;&#xD558;&#xB2E4;&#xACE0; &#xD568;.</p>
        <p>xmx &#xC635;&#xC158;&#xC744; &#xC124;&#xC815;&#xD558;&#xBA74; &#xD574;&#xB2F9;
          &#xC635;&#xC158;&#xC740; &#xBB34;&#xC2DC;&#xB418;&#xBA70; xmx &#xBCF4;&#xB2E4;&#xB294;
          &#xD574;&#xB2F9; &#xC635;&#xC158;&#xC744; &#xC8FC;&#xB294;&#xAC8C; &#xC88B;&#xB2E4;&#xACE0;
          &#xD568;.</p>
      </td>
      <td style="text-align:left">&#xB9AC;&#xC11C;</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:IntialRAMPercentage</td>
      <td style="text-align:left">&#xC571;&#xC774; &#xC2E4;&#xD589;&#xB420;&#xB54C; &#xCD08;&#xAE30; &#xD799;
        &#xC0AC;&#xC774;&#xC988; &#xC124;&#xC815;.
        <br />&#xC704;&#xC640; &#xB3D9;&#xC77C;&#xD558;&#xAC8C; double type</td>
      <td
      style="text-align:left">&#xB9AC;&#xC11C;</td>
    </tr>
    <tr>
      <td style="text-align:left"><del>-XX:+TraceClassUnloading</del>
      </td>
      <td style="text-align:left"><del>&#xD074;&#xB798;&#xC2A4;&#xB4E4;&#xC774; jvm &#xC5D0; &#xC5B8;&#xB85C;&#xB4DC; &#xB420;&#xB54C; &#xB85C;&#xADF8;&#xB97C; &#xCC0D;&#xC5B4;&#xC900;&#xB2E4;. <br />&#xBA54;&#xBAA8;&#xB9AC;&#xB9AD;&#xC774; &#xC758;&#xC2EC;&#xAC00;&#xB294; &#xD074;&#xB798;&#xC2A4;&#xB4E4;&#xC744; &#xD655;&#xC778;&#xD558;&#xAC70;&#xB098; &#xC624;&#xB798;&#xB41C; &#xD074;&#xB798;&#xC2A4;&#xB4E4;&#xC758; gc &#xC0C1;&#xD0DC; &#xD655;&#xC778;&#xAC00;&#xB2A5;.</del>
      </td>
      <td style="text-align:left"><del>&#xD14C;&#xC2A4;</del>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><del>-XX:+TraceClassLoading</del>
      </td>
      <td style="text-align:left"><del>&#xD074;&#xB798;&#xC2A4;&#xB4E4;&#xC774; jvm &#xC5D0; &#xB85C;&#xB4DC; &#xB420;&#xB54C; &#xB85C;&#xADF8;&#xB97C; &#xCC0D;&#xC5B4;&#xC900;&#xB2E4;. </del>
      </td>
      <td style="text-align:left"><del>&#xD14C;&#xC2A4;</del>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+AlwaysPreTouch</td>
      <td style="text-align:left">&#xBAA8;&#xB4E0; &#xBA54;&#xBAA8;&#xB9AC;&#xB97C; VM&#xC774; &#xC2DC;&#xC791;&#xD560;
        &#xB54C; &#xC218;&#xD589;.
        <br />jvm &#xC2DC;&#xC791; &#xC2DC;&#xC5D0;&#xB294; &#xB290;&#xB9AC;&#xC9C0;&#xB9CC;
        run &#xB3C4;&#xC911;&#xC5D0;&#xB294; &#xBE60;&#xB974;&#xB2E4;&#xACE0; &#xD55C;&#xB2E4;.</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintGCApplicationConcurrentTime</td>
      <td style="text-align:left">&#xC571;&#xC758; &#xCD1D; &#xC2E4;&#xD589;&#xC2DC;&#xAC04;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:+PrintGCApplicationStoppedTime</td>
      <td style="text-align:left">gc &#xB85C; &#xC778;&#xD574; &#xC571;&#xC774; &#xC791;&#xB3D9;&#xC744;
        &#xC911;&#xC9C0;&#xD55C; &#xC2DC;</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

### 

### 리서치가 추가적으로 필요한 jvm option

* 기본 값만으로도 충분한지
* 변경이 필요하다면 적절한 값은 어떻게 테스트해볼 수 있을

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xC635;&#xC158;</th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">-XX:NewRatio</td>
      <td style="text-align:left">g1gc &#xB97C; &#xC0AC;&#xC6A9; &#xC2DC; &#xBBF8; &#xC124;&#xC815; &#xAD8C;&#xC7A5;.</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:SurvivorRatio</td>
      <td style="text-align:left">g1gc &#xB97C; &#xC0AC;&#xC6A9; &#xC2DC; &#xBBF8; &#xC124;&#xC815; &#xAD8C;&#xC7A5;.</td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:MetaspaceSize</td>
      <td style="text-align:left">
        <p>&#xAC00;&#xBE44;&#xC9C0; &#xCEEC;&#xB809;&#xC158;&#xC744; &#xD2B8;&#xB9AC;&#xAC70;&#xD558;&#xB294;
          &#xBA54;&#xD0C0; &#xC2A4;&#xD398;&#xC774;&#xC2A4;&#xC758; &#xCD5C;&#xC18C;
          &#xD06C;&#xAE30;&#xB97C; &#xC9C0;&#xC815;&#xD55C;&#xB2E4;.</p>
        <p>&#xD604;&#xC7AC; &#xC0AC;&#xC6A9;&#xC911;&#xC778; &#xBA54;&#xD0C0;&#xC2A4;&#xD398;&#xC774;&#xC2A4;
          &#xD06C;&#xAE30; &#xD655;&#xC778; &#xD6C4; &#xC801;&#xC808;&#xD55C; &#xAC12;
          &#xC124;&#xC815;&#xD558;&#xBA74; &#xB420;&#xB4EF;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:MaxMetaspaceSize</td>
      <td style="text-align:left">
        <p>&#xCD5C;&#xB300; &#xBA54;&#xD0C0;&#xC2A4;&#xD398;&#xC774;&#xC2A4; &#xAC12;&#xC744;
          &#xC9C0;&#xC815;&#xD55C;&#xB2E4;. &#xC9C0;&#xC815;&#xD558;&#xC9C0; &#xC54A;&#xC744;
          &#xACBD;&#xC6B0; &#xC81C;&#xD55C;&#xC5C6;&#xC774; &#xB298;&#xC5B4;&#xB098;&#xAE30;
          &#xB54C;&#xBB38;&#xC5D0; &#xC2DC;&#xC2A4;&#xD15C; &#xC548;&#xC815;&#xC131;&#xC744;
          &#xC704;&#xD574; &#xC124;&#xC815;&#xD558;&#xB294;&#xAC8C; &#xC88B;&#xC744;&#xB4EF;
          &#xC2F6;&#xB2E4;. (&#xAD73;&#xC774; &#xC124;&#xC815;&#xD558;&#xC9C0; &#xC54A;&#xB294;&#xAC83;&#xB3C4;
          &#xAD8C;&#xC7A5;&#xD55C;&#xB2E4;&#xACE0; &#xD568;)</p>
        <p>&#xC9C0;&#xC815;&#xD55C; &#xAC12;&#xC5D0; &#xB3C4;&#xB2EC;&#xD558;&#xBA74;
          oome (&quot;meta data space..&quot;) &#xC5D0;&#xB7EC;&#xB97C; &#xBC49;&#xB294;&#xB370;
          &#xD55C;&#xB3C4;&#xC5C6;&#xC774; &#xB298;&#xC5B4;&#xB098;&#xB294; &#xBB38;&#xC81C;&#xBCF4;&#xB2E4;
          &#xD574;&#xB2F9; &#xAC12;&#xC5D0; &#xB3C4;&#xB2EC;&#xD574;&#xC11C; &#xC5D0;&#xB7EC;&#xAC00;
          &#xBC1C;&#xC0DD;&#xD588;&#xC744; &#xACBD;&#xC6B0; &#xC6D0;&#xC778;&#xC744;
          &#xCC3E;&#xC544;&#xC11C; &#xC218;&#xC815;&#xD558;&#xB294;&#xAC8C; &#xB354;
          &#xC88B;&#xB2E4;&#xACE0; &#xC0DD;&#xAC01;...</p>
        <p>&#xD574;&#xB2F9; &#xAC12;&#xC740; &#xC2E4;&#xC81C; &#xCEE4;&#xBC0B;&#xB418;&#xB294;
          &#xAC12;&#xC774; &#xC544;&#xB2C8;&#xACE0; &#xC0C1;&#xD55C;&#xC120;&#xC744;
          &#xC9C0;&#xC815;&#xD558;&#xB294; &#xAC83;&#xC774;&#xAE30; &#xB54C;&#xBB38;&#xC5D0;
          &#xCDA9;&#xBD84;&#xD788; &#xD070; &#xAC12;&#xC744; &#xC124;&#xC815;&#xD574;&#xB3C4;
          &#xB420;&#xB4EF;&#xD558;&#xB2E4;. (256m &#xB85C; &#xCD08;&#xAE30; &#xC124;&#xC815;
          &#xD6C4; &#xC774;&#xC288;&#xAC00; &#xC788;&#xB294;&#xC9C0; &#xD655;&#xC778;&#xD558;&#xB294;&#xAC83;&#xC744;
          &#xAD8C;&#xC7A5;&#xD55C;&#xB2E4;&#xACE0; &#xD568;.)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:MaxRAMPercentage</td>
      <td style="text-align:left">
        <p>&#xCEE8;&#xD14C;&#xC774;&#xB108;&#xC758; &#xBA54;&#xBAA8;&#xB9AC; &#xC0AC;&#xC774;&#xC988;&#xB97C;
          &#xAE30;&#xC900;&#xC73C;&#xB85C; &#xD799;&#xBA54;&#xBAA8;&#xB9AC; &#xC0AC;&#xC774;&#xC988;&#xAC00;
          &#xC801;&#xC6A9;&#xB41C;&#xB2E4;.</p>
        <p>pod &#xB0B4;&#xBD80; &#xD504;&#xB85C;&#xC138;&#xC2A4;&#xC6A9; &#xACF5;&#xAC04;&#xC744;
          &#xC704;&#xD574; 75~80% &#xB85C; &#xC815;&#xB3C4;&#xB9CC; &#xC801;&#xC6A9;&#xD558;&#xB294;&#xAC83;&#xC774;
          &#xAD8C;&#xC7A5;&#xB41C;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">-XX:IntialRAMPercentage</td>
      <td style="text-align:left">&#xBA54;&#xBAA8;&#xB9AC; &#xC0AC;&#xC6A9;&#xB7C9;&#xC774; &#xCD08;&#xAE30;
        &#xC694;&#xCCAD; &#xBA54;&#xBAA8;&#xB9AC;&#xBCF4;&#xB2E4; &#xB298;&#xC5B4;&#xB0A0;
        &#xACBD;&#xC6B0; &#xC624;&#xBC84;&#xD5E4;&#xB4DC; &#xBC1C;&#xC0DD;, gc
        &#xD0C0;&#xC784;&#xC774; &#xB298;&#xC5B4;&#xB0A0; &#xC218; &#xC788;&#xB2E4;&#xACE0;
        &#xD55C;&#xB2E4;. &#xC624;&#xBC84;&#xD5E4;&#xB4DC;&#xB97C; &#xC904;&#xC774;&#xAE30;
        &#xC704;&#xD574; MaxRAMPercentage &#xC640; &#xB3D9;&#xC77C;&#xD55C; &#xAC12;&#xC744;
        &#xC8FC;&#xB294;&#xAC83;&#xC774; &#xAD8C;&#xC7A5;&#xB428;.</td>
    </tr>
  </tbody>
</table>



> 설정된 jvm 옵션들 확인하는 커맨드 
>
> 힙, 메타스페이스 사이즈만 확
>
> ```text
> java -XX:+PrintFlagsFinal -version 2>&1 | grep -i -E 'heapsize|metaspacemsize|version'
> ```



참고

{% embed url="https://blog.gceasy.io/2018/12/23/usestringdeduplication/\#more-2861" %}



