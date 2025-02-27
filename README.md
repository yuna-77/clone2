# ArtCenter Nabi

> 동적인 Swiper 효과와 하단 게시판 기능을 활용해 이벤트 정보를 직관적으로 제공하고 지속적인 방문을 유도하는 Web을 만들었습니다.  
> [🔗 Site Link](https://artcenter-nabi.vercel.app/)

2024.08 ~

## Overview ⭐️

✅ 동적인 스와이퍼 효과를 메인 페이지에 적용   
✅ 전시회와 이벤트 정보를 한눈에 제공하고 사용자 참여를 유도   
✅ 하단 부에는 게시판 기능을 추가하여 이로인한 방문자들의 지속적인 사이트 방문 유도를 구성   
✅ 리액트를 사용하여 지속 가능한 데이터 관리와 콘텐츠 유지 보수의 편의성을 크게 향상   


## 사용 기술 스택 🔧

- **Frontend** : React, GSAP, HTML, CSS
- **Backend** : Node.js
- **Database** : ** MongoDB **
- **Library** : SwiperJS
- **SCM** : Git, GitHub
- **Deployment** : Vercel
- **Design** : Figma
- **Platform**: Web

    
## 주요 기능 ⚙️

### [ 메인 화면 ]

|Main Slide|
|:---:|
|<img src="public/images/Readme.image/main slide.png" />|
|기본적인 swiperJS를 응용하여 메인화면을 구성해보았다.|   

- 메인 페이지에 동적인 Swiper를 적용하여 보다 Interective Web을 보여주고자 했습니다.
- 가독성을 높이기 위해 component/Swiper.js 파일을 따로 만들어 컴포넌트를 분리했습니다.
```
	return(
		<>
			<Swiper
				speed={1000}
				loop={true}
				pagination={pagination}
				slidesPerView={1}

				modules={[Pagination]}
				className="gallery mainSwiper"
			>
				{
					data.swiper_slide.map((d,i) =>
						<SwiperSlide key={i}>
							<img src={`/images/${d.img}`} alt={d.alt}/>
							<div className="author">
								<span>{d.author[0]}</span>
								<span>{d.author[1]}</span>
							</div>
						</SwiperSlide>
					)
				}
			</Swiper>
			<div className="swiper-pagination"></div>
		</>
	);
```
- 슬라이드 방식의 전시회 소개는 메인 페이지에서 전시회에 대한 정보를 한눈에 볼 수 있게 합니다.
- 추가 이벤트가 생길 시에는 간단한 업데이트(react)로 지속적인 사이트 관리의 편의성을 높여줍니다.


### [ 탭 인터페이스 구현 ]

|Hover|
|:---:|
|<img src="public/images/Readme.image/tab.png" />|
|탭에 호버 기능 구현 |  

- 탭을 클릭하거나 마우스를 올렸을 때 나타나는 시각적 변화를 통해 사용성과 가독성을 높였습니다.
- 이 기능은 사이트 방문자들이 전시회를 더 쉽게 탐색하고 빠른 정보를 얻을 수 있도록 도와주는 역할을 합니다.

  #### [ 주요 기능 ]
  -**탭 호버 효과** : 각 탭에 마우스를 올리면 배경색과 콘텐츠 테두리 색상이 변화하여 사용자가 현재 탭에 마우스를 올렸다는 시각적 피드백을 제공합니다.
  ```
    #area2 ul li .content a .pic img {
	    display: block;
    	width: 100%;
    	height: 100%;
    	object-fit: cover;
    	transform: scale(1);
    	transition: transform 0.4s;
    }
    #area2 ul li .content a:hover .pic img,
    #area2 ul li .content a:focus .pic img {
    	transform: scale(1.1);
    }
  ```
  -**탭 활성화 기능** : 클릭된 탭은 active 클래스를 통해 강조 표시되며, 해당 탭에 맞는 콘텐츠가 화면에 표시됩니다.   
  -**직관적인 UI** : 탭 간의 전환을 쉽게 할 수 있도록 구성하여 사용자가 빠르게 원하는 내용을 찾아볼 수 있습니다.


### [ Video ]

- video API를 활용하여 관련 기능을 구현하였습니다.

### [ 게시판 ]

|Board list|
|:---:|
|<img src="public/images/Readme.image/board.png" />|
|table로 게시판을 만들어 보았다. td,tr등등 기본적요소를 활용했다.|

- 게시판 기능을 추가하여 사용자가 전시회 관련 정보나 의견을 자유롭게 나눌 수 있는 공간을 제공 하였습니다.
- css선택자를 사용하여 폼 디자인,콘텐츠의 유지 보수나 교체를 도와주었습니다.
- Node.js의 템플릿 엔진인 EJS를 사용하여 게시판 기능을 구현하였습니다.
- 사용자들이 미술관의 공지사항 및 소식을 쉽게 확인할 수 있도록 동적 게시판을 만들었으며 EJS로 서버에서 데이터를 효율적으로 렌더링 하였ㅅ브니다.
- 게시글 목록 조회, 검색 기능을 구현하였습니다.

## 후기 ⌨️

이번 미술관 사이트 리뉴얼 프로젝트는 웹에 대한 기초를 다질 수 있는 좋은 기회였습니다.

다양한 레이아웃과 애니메이션 효과를 적용하면서 CSS에 대한 이해도가 생겼고, 특히 동적인 웹 요소 구현 능력을 키웠습니다.

**서버와 데이터 연동을 이후에 추가하여 보완할 예정입니다.**

다음 프로젝트때는 백엔드 부분을 보완 해서 웹 구축하는것을 목표로 하겠습니다.
