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
π now we will start rust !

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
π make simple rest api using for rust

<div grid="~ cols-2 gap-16">
<div>
<div class='flex items-center justify-center'>
  <img border="rounded" src="https://nodejs.org/static/images/logos/nodejs-new-pantone-black.svg" class="w-50 bg-white"/>
</div>
  

  node.js ν¨ν€μ§ λ§€λμ λ₯Ό μ¬μ©ν΄μ νλ‘μ νΈ μννκΈ°
  ```bash
    yarn init <project-name>
    yarn init node-simple-api
  ```

  ```bash
    π¦ node-simple-api
    β π package.json
  ```

</div>
  
<div >
<div class='flex items-center justify-center'>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Rust_programming_language_black_logo.svg/144px-Rust_programming_language_black_logo.svg.png" class="h-30 bg-white text-center" />
</div>

  rust ν¨ν€μ§ λ§€λμ λ₯Ό μ¬μ©ν΄μ νλ‘μ νΈ μννκΈ°

```bash
  cargo new '<project-name>'
  cargo new rust-simple-api
```

```bash
  π¦ rust-simple-api
  β£ π .git
  β β£ π , , ,
  β£ π src
  β β π main.rs
  β£ π .gitignore
  β£ π Cargo.lock
  β π Cargo.toml
```
</div>

</div>

---

## Structure

```bash
  π¦ rust-simple-api
    β£ π src
    β β π config.rs
    β β π handlers.rs
    β β π main.rs
    β β π model.rs
```

<br/>

- config.rs : νκ²½ λ³μλ± μ€μ κ° κ΄λ ¨ μ½λ μμ±
- handlers.rs : router μ½λ μμ±
- main.rs : app init μ½λ μμ±
- model.rs : database κ΄λ ¨ μ½λ μμ±

## crates
###### μ€μ΅μ μν΄μ νμν λͺ¨λλ€

```bash
  cargo add actix-web diesel dotenv
```

---

## κ°λ¨ν μΉμλ² λ§λ€κΈ°

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

## μ΄λ»κ² νλκ±°μ§?

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


