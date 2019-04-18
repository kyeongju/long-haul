---
layout: post
title:  "기부를 위한 플리마켓  시스템"
date:   2019-04-16
description: 누구나 쉽게 기부를 하기 위한 플리마켓 형식의 기부 시스템입니다.
---
세계기부지수를 보면 대한민국은 다소 기부지수가 낮은 편입니다. 그 이유 중 하나가 어떻게 기부를 하여야 하는지, 기부의 투명성이 의심스러워서 입니다. 그래서 요즘 온라인을 통한 기부가 많이 활성화 되고 있고 온라인 쇼핑 시장이 점점 커지고 있는 것을 이용하여 누구든지 자신이 판매 하고자 하는 물품을 올려 직접 기부대상과 기부하고자 하는 금액을 입력할 수 있습니다. 그리고 물품이 판매가 되었을 때 직접 설정한 기부대상에게 판매금액의 일부가 기부되는 방식의 시스템입니다.

<h3>개발 내용</h3>
<p>개발기간: 2017.07 ~ 2017.10 (약 3개월)</p>
<p>개발인원: 4명</p>
<p>담당역할: (나중에적기)를 이용한 전반적인 UI설계및 레이아웃 컨트롤</p>
<p>플랫폼: Web</p>
<p>개발언어: HTML, CSS, Javascrip, Jquery</p>
<p>서버: Node.js</p>
<p>DBMS: MySQL</p>

<h3>프로젝트 설계</h3>

<!-- <figure>
	<img src="{{ '/assets/img/concept.jpg' | prepend: site.baseurl }}" alt="">
	<figcaption>Fig1. - Conceptual Diagram</figcaption>
</figure> -->

<figure>
	<img src="{{ '/assets/img/ClassDiagram1.jpg' | prepend: site.baseurl }}" alt="">
	<figcaption>Fig2-1. - ClassDiagram1</figcaption>
</figure>

<figure>
	<img src="{{ '/assets/img/ClassDiagram2.jpg' | prepend: site.baseurl }}" alt="">
	<figcaption>Fig2-2. - ClassDiagram2</figcaption>
</figure>

<!-- Fig2-1, 2-2는 ClassDiagram을 나타낸다. Fig2-1에서 회원이 되기위해 회원정보를 입력하고 회원가입을 한다. 마켓을 등록하기 위해서는 마켓의 이름, 이미지, 시작일, 종료일, 기부대상, 기부금액이 필요하고 물품을 등록하기 위해서는 물품 이미지, 이름, 가격, 카테고리, 가격, 설명을 등록하여야한다. 물품을 식별하기 위해서 물품 번호, 카테고리 코드, 판매처 번호, 판매상태를 선택하여야한다.
Fig2-2는 마이페이지 클래스 다이어그램을 나타낸다. 마이페이지에서는 주문내역, 판매처관리, 포인트이력, 마켓관리를 보여준다. -->


<figure>
	<img src="{{ '/assets/img/erd.png'}}" alt="" style="width:600px; height:420px;" >
	<figcaption>Fig3. - E-R Diagram</figcaption>
</figure>
Fig4는 ER다이어그램이다. 테이블로는 배송지, 회원_배송지, 회원, 마켓, 즐겨찾기, 기부단체, 기부대상, 주문, 포인트, 장바구니, 판매처, 피드백, 상품주문, 물품, 물품카테고리, 월별 우수회원통계로 구성되어있다. 회원이 정한 기부 대상으로 이미 진행되고 있는 마켓이 존재하면 등록이 제한된다. 마켓을 주최한 회원 역시 마켓의 판매처도 되어야 한다. 관리자의 판단에 따라 마켓의 상태는 대기, 진행, 실패가 될 수 있다. 마켓의 상태가 실패일 시 주최자는 수정을 통해 다시 마켓 등록을 신청할 수 있다. 기부금액은 판매자의 마켓 수익금 중 순수 이익을 제외한 기부 금액이 대상이다.


<h3>개발 결과</h3>

<figure>
<img src="{{ '/assets/img/main.png' | prepend: site.baseurl }}" alt="" style="width:600px; height:auto;">
<figcaption>그림1. - 메인화면</figcaption>
</figure>
<figure>
		<img src="{{ '/assets/img/goodsbuy.png' | prepend: site.baseurl }}" alt="" style="width:600px; height:420px;" >
		<figcaption>그림1-1. - 물품구매</figcaption>
</figure>
그림1은 메인화면이다. 메인화면에는 기부대상에 대한 카테고리, 기부대상, 기부율을 확인할 수 있다. 구매자는 기부하고 싶은 대상을 클릭하면 해당 기부대상의 마켓 물품들을 확인하고 구매할 수 있다.그림1-1은 물품을 구매하는 화면이다.

<figure>
<img src="{{ '/assets/img/marketresi.png' | prepend: site.baseurl }}" alt="" style="width:600px; height:auto;">
<figcaption>그림2. - 마켓등록</figcaption>
</figure>
<figure>
	<img src="{{ '/assets/img/marketreq.png'}}" alt="" style="width:600px; height:auto;">
	<figcaption>그림3 - 마켓승인요청</figcaption>
</figure>
그림2는 마켓등록 화면이다. 주최자는 플리마켓을 열기위해 로그인인을 하고 기부대상 카테고리를 정한다. 그리고 마켓에 필요한 정보들을 입력한다. 등록이 완료되면 그림3에서 승인요청을 클릭하면 관리자의 승인을 기다리고 승인이 완료되면 마켓을 진행할 수 있다.

<figure>
	<img src="{{ '/assets/img/goodsresi.png'}}" alt="" style="width:600px; height:auto;">
	<figcaption>그림4 - 물품등록</figcaption>
</figure>
<figure>
	<img src="{{ '/assets/img/goodslist.png' | prepend: site.baseurl }}" alt="" style="width:600px; height:auto;">
	<figcaption>그림5 - 물품목록</figcaption>
</figure>
그림4는 물품사진, 이름, 가격, 카테고리, 수량, 물품에 대한 설명을 작성하여 물품을 등록하는 화면이다.
그림4에서 등록한 물품들을 그림5 물품목록 화면에서 볼 수 있다. 화면에는 물품의 사진, 이름, 가격 그리고 판매처에 대한 정보, 기부반영 퍼센트를 볼 수 있다.

<figure>
		<img src="{{ '/assets/img/mypage1.png'}}" alt="" style="width:600px; height:auto;">
		<figcaption>그림6-1 - 마이페이지</figcaption>
</figure>
<figure>
		<img src="{{ '/assets/img/mypage2.png'}}" alt="" style="width:600px; height:auto;">
		<figcaption>그림6-2 - 마이페이지</figcaption>
</figure>

그림6-1, 6-2는 마이페이지 화면이다. 주문내역과 포인트 이력을 확인할 수 있다.


<!-- <table class="type11">
    <tbody>
    <tr>
        <td>

          <img src="{{ '/assets/img/main.png' | prepend: site.baseurl }}" alt="">
          <figcaption>메인화면</figcaption>

        </td>
        <td>

          <img src="{{ '/assets/img/marketresi.png' | prepend: site.baseurl }}" alt="">
          <figcaption>마켓등록</figcaption>

        </td>
        <td>

           <img src="{{ '/assets/img/marketmanage.png' | prepend: site.baseurl }}" alt="">
           <figcaption>마켓관리</figcaption>

        </td>
    </tr>

    <tr>
        <td>

          <img src="{{ '/assets/img/goodslist.png' | prepend: site.baseurl }}" alt="">
          <figcaption>물품목록</figcaption>

        </td>
        <td>

          <img src="{{ '/assets/img/goodsbuy.png' | prepend: site.baseurl }}" alt="">
          <figcaption>물품구매</figcaption>

        </td>
        <td>

           <img src="{{ '/assets/img/feedback.png' | prepend: site.baseurl }}" alt="">
           <figcaption>피드백관리</figcaption>

        </td>
    </tr>

    <tr>
        <td>

          <img src="{{ '/assets/img/mypage1.png' | prepend: site.baseurl }}" alt="">
          <figcaption>마이페이지</figcaption>

        </td>
        <td>

          <img src="{{ '/assets/img/mypage2.png' | prepend: site.baseurl }}" alt="">
          <figcaption>마이페이지</figcaption>

        </td>

    </tr>


    </tbody>
</table> -->

<!-- <style>
		table.type11 {
			border-collapse: separate;
			border-spacing: 1px;
			text-align: center;
			line-height: 1.5;
			margin: 20px 10px;
		}
		table.type11 th {
			width: 155px;
			padding: 10px;
			font-weight: bold;
			vertical-align: top;
			color: #fff;
			/* background: #ce4869 ; */
		}
		table.type11 td {
			width: 155px;
			padding: 10px;
			vertical-align: top;
			border-bottom: 1px solid #ccc;
			/* background: #eee; */
		}
</style> -->

<h3>관련기술</h3>
<h4 style="text-align:center">기술조사하기</h4>



<!-- <figure>
	<img src="{{ '/assets/img/mvc.png' | prepend: site.baseurl }}" alt="" style="width: 300px; height: 300px;">
	<figcaption>MVC패턴</figcaption>
</figure> -->

-------설명적기------

1. List Item
2. Longer List Item
    1. Nested OL Item
    2. Another Nested Item
3. List Item



Donec id elit non mi porta gravida at eget metus. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas faucibus mollis interdum. Donec sed odio dui. Cras justo odio, dapibus ac facilisis in, egestas eget quam.