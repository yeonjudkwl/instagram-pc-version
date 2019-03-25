# Instagram PC버전 만들어보자
> html, css를 이용하여 만들어봅니다.

## 1. Header를 만들어보자
> Header에는 로고와 검색창 그리고 nav가 들어갑니다.


우선 `index.html`파일을 하나 만들어봅시다.
```
<!DOCTYPE html>
<html>
<head>
    <title>instagram</title>
</head>
<body>
    <header>
        <div class="logo">
            
        </div>
        <div class="search">
           
        </div>
        <nav>
            
        </nav>
    </header>
</body>
</html>
```
`<header>`에 2개의 `div`와 `nav`를 만들어줍니다.
첫 번째 `div`에 `class="logo"`
두 번째 `div`에 `class="search"`라고 이름을 지어줍니다.

```
<div class="logo">
    <img src="images/instagrams.png" alt="" class="instagram_logo">
</div>
```
`img`를 넣어주고 `class="instagram_logo"`라는 이름을 붙여줍니다. 
나중에 이 `class`이름을 통해 크기를 조정할 수 있어요.

```
<div class="search">
    <input type="text" value="검색">
</div>
```
`input`을 통해 사용자의 입력을 받을 수 있도록 합니다.


```
<nav>
    <ul>
        <li><img src="images/compass.svg" alt="" class="logo_img"></li>
        <li><img src="images/heart.svg" alt="" class="logo_img"></li>
        <li><img src="images/profile.svg" alt="" class="logo_img"></li>
    </ul>
</nav>
```
`ul`과 `li`를 통해 nav를 만듭니다. 
인스타를 보면 이미지로 되어있죠? 우리도 이미지를 넣어보도록 하겠습니다.
그리고 크기를 조절하기 위해 `class="logo_img"`라는 이름을 미리 붙여줍니다.


`html`로 밑그림을 다 그렸으니 이제 색칠을 해봐야겠죠?
`css`작업을 해보도록 합시다.

### 1-2. Header CSS 작업하기

`style.css`파일을 만들어 줍니다.
```
<!DOCTYPE html>
<html lang="en">
<head>
    <title>instagram</title>
    <link rel="stylesheet" href="./style.css">
</head>
</html>
```
`html`파일의 `head`부분에 `<link rel="stylesheet" href="./style.css">`로 파일을 불러옵니다.

`style.css`파일에서
```
body{
    margin:0;
    padding:0;
    background-color: #fafafa;
}
header{
    height: 80px;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    border-bottom: 1px solid #DBDBDB;
    background-color: #ffffff;
}
.instagram_logo{
    width: 165px;
}
.search input{
    width: 200px;
    padding: 5px;
    border:1px solid #DBDBDB;
    border-radius: 5px;
    background-color:#fafafa;
    text-align: center;
    color: #999999;
}
.logo_img{
    width: 25px;
    padding: 10px;
    padding-right: 0;
}
ul{
    display: flex;
    list-style: none;
}
li{
    margin-right: 25px;
}
```
`header`에 `display:flex;`를 적용시켜 준 후, `justify-content`와 `align-items`를 통해 가로 세로 정렬을 해줍니다.
그리고 아까 지정해놓은 `class`를 통해 각 이미지의 크기 및 여백을 지정해 줍니다.

![../img/instagram_header.jpg](../img/instagram_header.jpg)

이러게 나오면 header는 완성!!!



## 2. content 만들어보기 
> `display:flex`를 이용하자

```
<body>
    <div class="con_wrap">
        <div class="conA">
            ...
            ...instagram의 contents 내용이 들어갑니다.
        </div>
        <div class="conB">
           ...
           ...profile, story, 추천 친구 목록이 들어갈거에요.
        </div>
    </div>
</body>
```
내용이 들어갈 `div` 2개를 만들어 준 후,
`div class="con_wrap"`으로 감싸줍니다.

### 2-1. con_wrap CSS 작업하기

```
.con_wrap{
    display: flex;
    justify-content: center;
    align-items: flex-start;
    margin-top: 50px;
    padding: 0 290px;
}
.conA{
    flex: 2;
    margin: 10px 0;
}
.conB{
    flex: 1;
}
```
`div class="con_wrap"`에 `display:flex;`를 적용하여 내부 `div`들이 옆으로 쌓이게 해줍니다.
`flex`를 통해 `conA`:`conB`=2:1로 비율을 지정해줍니다.



## 3. conA 내용채우기

```
<div class="conA">
    <div class="con">
        <div class="title">
            ... 이미지와 이름이 들어갑니다
        </div>
        메인 이미지가 들어갑니다.
        <div class="logos">
            <div class="logos_left">
                좋아요, 댓글, 공유 logo가 들어갑니다.
            </div>
            <div class="logos_right">
                북마크 logo가 들어갑니다.
            </div>
        </div>
        <div class="content">
            좋아요 수, 댓글, 댓글 입력창이 들어갑니다.
        </div>
    </div>
</div>
```
`conA`안에 들어갈 내용들을 생각하여 `div`로 틀을 만들어 줍니다.

>title에는 프로필사진과 이름이 들어갑니다.
```
<div class="title">
    <img src="images/hong.png" alt="" class="img">
    <p>yeonju</p>
</div>
```

>메인 이미지를 넣어줍니다.
```<img src="images/picture.png" alt="" class="con_img">
```

>각 logo들을 넣어줍니다.
```
<div class="logos">
    <div class="logos_left">
        <img src="images/heart.svg" alt="" class="logo_img">
        <img src="images/speech-bubble.svg" alt="" class="logo_img">
        <img src="images/upload.svg" alt="" class="logo_img">
    </div>
    <div class="logos_right">
        <img src="images/bookmark.svg" alt="" class="logo_img">
    </div>
</div>
```
`div`로 오른쪽에 들어갈 logo와 왼쪽에 들어갈 logo를 지정해줍니다.


>이미지 밑에 좋아요 수, 해시태그, 댓글창이 들어갑니다.
```
<div class="content">
    <p><b>좋아요 80개</b></p>
    <p><a href="">yeonju</a>#해달 #html #css</p>
    <input type="text" name="" id="" value="댓글달기">
</div>
```

### 3-1. conA css 작업하기
```
.conA .con{
    width: 600px;
    height: 920px;
    margin-bottom: 50px;
    border: 1px solid #DBDBDB;
    border-radius: 3px;
    background-color: #ffffff;
}
.title{
    display: flex;
    margin: 10px;
}
.title p{
    margin: 5px 15px;
    font-size: 20px;
}
.con_img{
    width: 600px;
}
.img{
    width: 50px;
    height: 50px;
    border-radius: 50%;
}
.logos{
    display:flex;
    justify-content: space-between;
    padding: 0 10px;
}
.content{
    padding: 10px;
}
.content input{
    width: 100%;
    height: 45px;
    border: none;
    border-top: 1px solid #DBDBDB;
    color: #999999;
    font-size: 16px;
}
.content input:focus{
    outline: none;
}
```
`input:focus`는 입력창에 클릭했을 때 파란테두리가 나타나는데 `outline: none;`을 해주면 파란테두리가 없어집니다.

        





[생활코딩](https://opentutorials.org/course/1)