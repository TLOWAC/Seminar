---
fonts:
  # basically the text
  sans: 'Robot'
  # use with `font-serif` css class from windicss
  serif: 'Robot Slab'
  # for code blocks, inline code, etc.
  mono: 'Fira Code'

layout: cover
# background: https://images.unsplash.com/photo-1562804501-74f1d98e65cc?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MzZ8fHJ1c3R8ZW58MHx8MHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60

---

# Simple Rust API Server
### Danbi-Korea SW Developer TLOWAC

---

## Rust Setting 
📔 now we will start rust !

<br/>

### [1. Install Rust ( for MACOSX )](https://www.rust-lang.org/tools/install)
```ts 
  curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

<br/>
<br/>

### 2. Checked Cargo
```ts 
  cargo --version  
```


<br/>
<br/>

### 3. Checked Rust
```ts 
  rustc --version  
```

<br/>
<br/>

---

## Project Setting
📔 make simple rest api using for rust

<div grid="~ cols-2 gap-16">
<div>
<div class='flex items-center justify-center'>
  <img border="rounded" src="https://nodejs.org/static/images/logos/nodejs-new-pantone-black.svg" class="w-50 bg-white"/>
</div>
  

  node.js 패키지 매니저를 사용해서 프로젝트 셋팅하기
  ```bash
    yarn init <project-name>
    yarn init node-simple-api
  ```

  ```bash
    📦 node-simple-api
    ┗ 📜 package.json
  ```

</div>
  
<div >
<div class='flex items-center justify-center'>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Rust_programming_language_black_logo.svg/144px-Rust_programming_language_black_logo.svg.png" class="h-30 bg-white text-center" />
</div>

  rust 패키지 매니저를 사용해서 프로젝트 셋팅하기

```bash
  cargo new '<project-name>'
  cargo new rust-simple-api
```

```bash
  📦 rust-simple-api
  ┣ 📂 .git
  ┃ ┣ 📂 , , ,
  ┣ 📂 src
  ┃ ┗ 📜 main.rs
  ┣ 📜 .gitignore
  ┣ 📜 Cargo.lock
  ┗ 📜 Cargo.toml
```
</div>

</div>

---

## Structure

```bash
  📦 rust-simple-api
    ┣ 📂 src
    ┃ ┗ 📜 config.rs
    ┃ ┗ 📜 handlers.rs
    ┃ ┗ 📜 main.rs
    ┃ ┗ 📜 model.rs
```

<br/>

- config.rs : 환경 변수등 설정값 관련 코드 작성
- handlers.rs : router 코드 작성
- main.rs : app init 코드 작성
- model.rs : database 관련 코드 작성

## crates
###### 실습을 위해서 필요한 모듈들

```bash
  cargo add actix-web diesel dotenv
```

---

## 간단한 웹서버 만들기

```bash
async fn index()-> Reponder{
  HttpResponse.Ok().body("hello world")
}

#[actix_web::main]
async fn main() -> std::io::Result<()> {
    HttpServer::new(|| {
        App::new()
            .route("/", web::get().to(index))
    })
    .bind(("127.0.0.1", 9000))?
    .run()
    .await
}
```

<br/>


![image](https://user-images.githubusercontent.com/58043975/144236889-82693829-13ac-4493-8a15-864c53989fa4.png)


---

## 어떻게 하는거지?

- ##### scale up route 
- ##### distribute handler
- ##### res, req logging
- ##### error handling
- ##### route guard
- ##### authorization

---

# useful links

- [The Rust Programming Language ( KR )](https://rinthel.github.io/rust-lang-book-ko/ch01-03-hello-cargo.html)
- [The Fastest Web Framwork](https://www.techempower.com/benchmarks/#section=data-r20&hw=ph&test=fortune)
- [namu  wiki](https://namu.wiki/w/Rust#s-3.1)

- [ms official rust guide for beginner](https://docs.microsoft.com/ko-kr/learn/modules/rust-introduction/)
- [[ Tutorial ] Tour of Rust](https://tourofrust.com/00_ko.html)


