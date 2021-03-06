승현이는 넓은 정사각형 모양의 토지를 소유한 농부입니다. 농사를 편하게 짓고 싶었던 승현이는 토지 전체를 $5 \times R$행 $5 \times C$열의 격자로 나누었습니다. 그래도 뭔가 부족하다고 생각한 승현이는 5개의 행마다 가로로 (수평하게) 세워진 울타리를 놓고, 5개의 열마다 세로로 (수직하게) 세워진 울타리를 놓았습니다. 모든 울타리는 토지의 폭 전체를 가로질러야 합니다. 이렇게 세워진 울타리는 토지 전체를 5행 5열짜리 *구역*들로 나누고, 구역은 총 $R\times C$개 있습니다.

승현이가 농사를 지으면서 겪는 어려움은 새들의 출몰과 심한 가뭄입니다. 새들이 작물을 먹는 것을 방지하기 위해, 승현이는 몇 개의 구역에 허수아비를 설치해 놓았습니다. 허수아비는 (존재한다면) **한 개의 격자**를 차지하며 **각 $5 \times 5$ 크기 격자에 많아야 하나의 허수아비만** 존재합니다.

<table style="width: 100%; margin-bottom: 10px"><tr>
	<td style="width: 33%;"><img src="https://s3.ap-northeast-2.amazonaws.com/oj.uz/old/CEOI13_watering/fig1-1.png" style=""/></td>
    <td style="width: 33%;"><pre style="margin-left: 5px; margin-right: 5px;">.....|.....
.....|.....
...#.|.....
.....|.....
.....|.....
-----+-----
.....|.....
.....|.....
.....|.....
.....|.....
.....|.....</pre></td>
    <td><pre style="margin-left: 5px; margin-right: 5px;">aaacc|dxxxa
bbbce|dyyya
ddd#e|dzzza
ccbae|fccbb
cbbaa|ffcdb
-----+---_-
ssrrr|tttdd
saaax_xxeee
yxbbb|zdaaa
yxccc|zdbbb
yxddd|zdccc
</pre></td>
</tr></table><p class="small-text">[그림 1] 왼쪽에서부터: 승현이가 소유한 땅의 이미지 형태, 승현이가 소유한 땅의 텍스트 형태, 이 토지에다 스프링클러를 놓을 수 있는 방법 중 하나</p>

안타깝게도 승현이의 토지에만 몇 달 동안 지속될 것으로 보이는 가뭄이 들었고, 승현이는 각 격자에 스프링클러를 둬서 작물에 물을 주기로 했습니다. 각 스프링클러는 **정확히 3개의 노즐**을 가지고 있으며 모든 노즐에서 물을 뿌릴 수 있습니다. 이 중 하나는 주요 노즐이고, 나머지 두 개는 몸통 노즐입니다. 몸통 노즐들은 항상 **주요 노즐과 접해 있는 격자들 중 두 개**를 차지합니다. 따라서 스프링클러의 모양은 아래 6개 중 하나일 것입니다.

<div style="text-align: center; margin-bottom: 10px;"><img src="https://s3.ap-northeast-2.amazonaws.com/oj.uz/old/CEOI13_watering/fig2.png" style=""/><p class="small-text"></p></div>

승현이는 스프링클러를 적당히 설치하여 **토지의 허수아비가 없는 각 격자에 스프링클러의 노즐이 정확히 하나씩 있도록** 하고 싶습니다. 허수아비가 서 있는 격자에는 **스프링클러 노즐이 있으면 안 됩니다.** 또한 노즐들은 승현이의 토지 밖에 설치할 수 없습니다.

한 개의 스프링클러가 차지하는 세 개의 격자는 반드시 한 구역 내에 있을 필요는 없으며, 이웃한 두 구역을 차지할 수도 있습니다. 이러한 경우에 승현이는 **같은 스프링클러가 차지하는 격자들 중 서로 다른 구역에 있는 이웃한 두 격자 사이의 울타리에 구멍을 뚫습니다.** 구멍을 뚫는 것은 승현이에게 너무 힘든 일이기 때문에 승현이는 너무 많은 구멍을 뚫고 싶어 하지 않습니다. (왜 설치했는지는 넘어갑시다.)

### 해야 할 일

승현이가 소유한 토지에 대한 정보가 주어질 때 여러분은 스프링클러를 배치하는 유효한 방법을 찾아내야 합니다. 만약 올바른 방법을 찾아낸다면, 여러분이 받을 점수는 울타리에 뚫린 구멍의 수에 따라 결정됩니다. - 자세한 것은 아래의 '채점 기준'을 참고하세요.

이 문제는 Output-Only 문제입니다. 여러분에게 10개의 입력 파일이 주어지고 여러분은 이 입력 파일에 대한 출력 파일만 제작하시면 됩니다. 여러분은 입력 파일을 [여기](https://s3.ap-northeast-2.amazonaws.com/oj.uz/old/CEOI13_watering/watering.zip)에서 내려받을 수 있습니다.

입력 파일 `watering.in.X`에 대해 출력 파일 `watering.out.X`를 만든 뒤 하나의 zip 파일에 압축해서 제출하시면 됩니다.

주어진 입력 데이터에 대해서 유효한 방법이 항상 존재함이 보장됩니다. 여러 개의 유효한 방법이 존재한다면, 그 중 아무거나 제출하시면 됩니다.

### 입력

입력의 첫 번째 줄에는 승현이가 소유한 토지의 행의 수 $R$과 열의 수 $C$ ($1 \le R,C \le 100$)이 공백을 사이로 두고 주어집니다.

이후 $6 \times R - 1$개 줄이 주어지고, 각 줄에는 길이가 $6 \times R - 1$인 문자열이 주어집니다. 이들은 승현이의 토지와 토지에 설치된 울타리에 대한 정보를 나타냅니다. 울타리는 굉장히 얇지만 편의상 문자 하나로 표현합니다.

격자 하나는 문자 하나로 표현됩니다. 온점 ('`.`')은 빈 격자를, 해시 기호(샵, '`#`', 아스키 코드 35)는 허수아비가 설치된 격자를 나타냅니다. 수직하게 설치된 울타리는 '`|`'(아스키 코드 124)로, 수평하게 설치된 울타리는 '`-`'(음의 기호)로 나타냅니다. '`+`' 문자는 직교하는 두 울타리의 교차점을 나타냅니다.

### 출력

각 출력 파일으로 주어진 토지에 스프링클러를 배치하는 유효한 방법을 텍스트로 나타내서 출력해야 합니다. 울타리에 뚫린 구멍들은 언더바 (underscore, '`_`')로 나타내야 합니다. 입력 파일의 빈 격자 (온점 기호)들은 아래 규칙을 만족하도록 모두 알파벳 소문자 (`a`, `b`, ..., `z`)로 치환하여 출력해야 합니다.

1. 같은 스프링클러가 설치된 세 개의 격자는 한 구역에 있지 않더라도 같은 알파벳 으로 나타내야 합니다. 
2. 만약 **같은 구역의** 인접한 두 격자에 다른 스프링클러가 설치되어 있다면, 이 두 격자는 서로 다른 알파벳으로 나타내야 합니다.
3. 만약 **서로 다른 구역에 있는** 인접한 두 격자에 **다른 스프링클러가 설치되어 있고** 그 사이 울타리에 **구멍이 뚫려 있다면** 이 두 격자는 서로 다른 알파벳으로 나타내야 합니다.
4. 위의 세 가지 규칙을 모두 만족한다면, 서로 다른 구역에 있는 인접한 두 격자를 같은 알파벳으로 나타내도 됩니다.

### 채점 기준

각 테스트 케이스에는 10점의 점수가 배당되어 있습니다. 만약 여러분의 출력 데이터가 유효하지 않다면 해당 데이터에 대해 0점이 주어집니다. 만약 유효하다면, 아래 채점 기준에 따라 점수가 매겨집니다.

* 만약 울타리에 뚫린 구멍의 수가 $R \times C$ 이하라면 10점이 주어집니다.
* 그렇지 않다면 5점이 주어집니다.
* 10개 중 4개의 입력 데이터에서 모든 구역에 허수아비가 하나씩 설치되어 있습니다.

### 예제

<table class='table table-bordered table-condensed'>
 <thead>
  <tr>
   <th>입력</th>
   <th>출력</th>
  </tr>
 </thead>
 <tbody>
  <tr class="code-font">
   <td style="width: 50%;">2 2<br/>
.....|.....<br/>
.....|.....<br/>
...#.|.....<br/>
.....|.....<br/>
.....|.....<br/>
-----+-----<br/>
.....|.....<br/>
.....|.....<br/>
.....|.....<br/>
.....|.....<br/>
.....|.....</td>
   <td>aaacc|dxxxa<br/>
bbbce|dyyya<br/>
ddd#e|dzzza<br/>
ccbae|fccbb<br/>
cbbaa|ffcdb<br/>
-----+-----<br/>
ssrrr|tttdd<br/>
saaax_xxeee<br/>
yxbbb|zdaaa<br/>
yxccc|zdbbb<br/>
yxddd|zdccc</td>
  </tr>
 </tbody>
</table>
