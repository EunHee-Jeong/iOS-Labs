# ๐ ํธ์ ์๋ฆผ

iOS ์ฑ์์ ์ฌ์ฉ์์ ๊ด์ฌ์ ๋๋ ๋ฐฉ๋ฒ ์ค ํ๋์ด๋ค.

<br>

## ์ข๋ฅ

- Local Notification - ๋ก์ปฌ ํธ์, **์ฑ ์์ฒด์์ ๋ณด๋ด๋ ๊ฒ.** **์ ํด์ง ์๊ฐ์ ๋์ผํ ๋ฌธ๊ตฌ๋ก ์ ๋ฌ**ํ๊ณ  ์ถ์ ๊ฒฝ์ฐ
    - ์์
        - ํน์  ์๊ฐ๊ณผ ๋ ์ง์ ๋ง์ถฐ ์๋ฆผ ์ ๋ฌ
            
            โ ๋ก์ปฌ ๊ธฐ๊ธฐ ๋ด์์ ์์ธกํ  ์ ์๋ ๊ฒฝ์ฐ
            
- Remote Notification - ์๋ฒ ํธ์, **์๋ฒ์์ ๋ณด๋ด๋ ๊ฒ**, **๋ถ์์ ๋ฐ์ํ ์๋ฐ์ดํธ๋ฅผ ์ ๋ฌ**ํ๊ณ  ์ถ์ ๊ฒฝ์ฐ
    - ์์
        - ํน์  ์ฌ์ฉ์๋ฅผ ์ถ๋ ค๋ด์ด ํด๋น ์ฌ์ฉ์์๊ฒ๋ง ์๋ฆผ ์ ๋ฌ
        - ํน์  ์ฌ์ฉ์๊ฐ ํน์  ํ๋์ ํ ์์ ์ ์๋ฆผ ์ ๋ฌ
        - ์ธ์  ์ด๋ค ์ปจํ์ธ ๊ฐ ๋ด๊ธธ์ง ๋ชจ๋ฅด๋ ์ํฉ์ ์๋ฆผ ์ ๋ฌ
            
            โ **๋ก์ปฌ ๊ธฐ๊ธฐ ์์ฒด๋ง์ผ๋ก๋ ์์ธกํ  ์ ์๋ ๊ฒฝ์ฐ**
            
    - ๋ฐฑ์ค๋(์๋ฒ) ์์ญ์์ ํน์  ์์ ์ ๋ฐ์กํด์ค์ผ ํ๋ค.

<br>

## ์ ์ก ๋ฐฉ์

Provider (server) โ APNs โ iOS / watchOS / tvOS / macOS โ ClientApp

- ๋ก์ปฌํธ์์ Provider, APNs๊ฐ ๋ํด์ง ๊ฒ์ด ์๋ฒํธ์๋ค.


<br>

### 1. ๋ก์ปฌ ํธ์ ๊ตฌํ

- ์๋ฆผ ์์ฒญ (UNNotificationRequest) ๊ฐ์ฒด ์์ฑ

    - identifier (๊ฐ๊ฐ์ ์์ฒญ ๊ตฌ๋ถ, ์ค๋ณต๋์ง ์๋ ๊ณ ์ ์ id)
    
    - content (์๋ฆผ์ ๋ํ๋  ๋ด์ฉ๋ค โ ์๋ฆฌ๋ ๋ฐฐ์ง, ๋ฌธ์์ด ๋ฑ)
    
    - trigger (์กฐ๊ฑด, ์๋ฆผ์ด ์ด๋ค ๊ธฐ์ค์์ ๋ฐ์ก๋  ์ง ์ ํจ โ ๋ฌ๋ ฅ(๋ ์ง), ์๊ฐ, ์ฌ์ฉ์์ ์์น)
    
- UNNotificationCenter์ ์๋ฆผ ์์ฒญ ์ถ๊ฐ (Request)

    - ์ ์ ํ ์๊ฐ(= trigger์ ํด๋น)์ ์๋ฆผ ๋ณด๋ด์ค

### 2. ์๋ฒ ํธ์ ์๋ฆฌ

- **APNs**

    - Apple Push Notification Service์ ์ค๋ง๋ก, Remote Notification์ ์ฌ์ฉํ๊ธฐ ์ํ ํต์ฌ์ด๋ค.
    
        - ์๊ฒฉ ์๋ฆผ์ ๋ณด๋ผ ๋๋ ์๋ฒ์์ ๋ฐ๋ก ๊ธฐ๊ธฐ๋ก ๋ณด๋ด๋ ๊ฒ์ด ์๋๋ผ APNs๋ฅผ ๊ฑฐ์ณ์ผ ํ๊ธฐ ๋๋ฌธ
        
        - Provider (server) โ APNs โ device
        
    - ์๋ฆผ์ ์ ์ฅํ๊ณ  ์ ๋ฌํ๊ธฐ ๋๋ฌธ์ ๊ธฐ๊ธฐ์ ์ํฉ์ ๋ฐ๋ผ ์๋ฆผ์ ์ฒ๋ฆฌํด์ฃผ๋ ๊ด๋ฆฌ์ผํฐ ์ญํ ์ ํ๋ค.
    
    - ์์ฒด ๋ณด์ ์ํคํ์ฒ๋ฅผ ํตํด ์๊ฒฉ ์๋ฆผ์ ์์ ํ๊ฒ ์ ์ดํด ๋ณด์ ์์ค์ ์ ์งํ๋ค.
    
        - ์ ๋ขฐ ์์ค ๋ ๊ฐ์ง โ connection trust, device token trust
        
            - connection trust
            
                - Provider์ APNs ์ฌ์ด ๋๋ APNs์ device ์ฌ์ด์์ ์๋
                
                    - token-based : ์ ํจํ ์ธ์ฆํค
                    
                    - certificate-based : ์ ํจํ ์ธ์ฆ์ (SSL)
                    
            - device token trust
            
                - ๊ฐ ์๊ฒฉ ์๋ฆผ์์ end-to-end๋ก ์๋ํ๋ค.
                
                    - ๋ง ๊ทธ๋๋ก ๋(์ ๊ณต์)์์ ๋(์ฅ์น)์ผ๋ก ์๋ํ๋ ๊ฒ.
                    
                    - ๋ ์์ ์์๋ง ๋ผ์ฐํ๋๋๋ก ํด์ฃผ๋ ๊ฒ์ด๋ค.
                    
    - ๊ฐ ์ง์ ์์ ์๊ฒฉ ์๋ฆผ์ ๋ณด๋ด๋ ๊ณผ์ 
    
        - APP โ ์๊ฒฉ ์๋ฆผ ์ฌ์ฉ์ ์ํด APNs์ ๋ฑ๋กํ๊ณ  โ ์ฅ์น์ ๊ณ ์ ํ ํ ํฐ์ ๋ฐ๊ธ ๋ฐ์์ โ ํด๋น Provider์๊ฒ ์ ๋ฌํ๋ค.
        
        - Provider โ ์ฐ๊ฒฐ๋ ํ ํฐ์ ํด๋นํ๋ ๊ฐ๊ฐ์ push ์์ฒญ + ์ฅ์น ํ ํฐ์ ํฌํจํด โ APNs๋ก ์ ๋ฌ
        
        - APNs โ ํ ํฐ์ ํฌํจ๋ Provider์ ์์ฒญ ํ์ธ โ push๊ฐ ๊ณ ์ ํ device์๋ง ์ ๋ฌ๋๋๋ก ์กฐ์ 
        

- **Firebase Cloud Messaging (FCM)**

    - Remote Notification์ ์์ฝ๊ฒ ๊ด๋ฆฌํ๊ณ  ์ ์กํ  ์ ์๋ Firebase platform์ ๋งํ๋ค.
        
        ํ๋ง๋๋ก ์๊ฒฉ ์๋ฆผ์ ๋ณด๋ผ ์ ์๋๋ก ๋์์ฃผ๋ ๋๊ตฌ์ด๋ค.
        
    - ์ฌ์ฉ ์
    
        - APNs์ ๋ณด์ ์๊ฑด์ ๊ฐ์ถ ์๋ฒ๋ฅผ ์ง์  ๊ตฌ์ถํ๊ธฐ ํ๋ค ๋
        
        - ํด๋ผ์ด์ธํธ ๊ฐ๋ฐ์๋ก์ ์๋น์ค์ ์ฑ ์์ฒด์๋ง ์ง์คํ๊ณ  ์ถ์ ๋
            
            โ ์ฆ Provider (์๋ฒ)์ ์ญํ ์ ๋์  ํด์ฃผ๋ ๊ฒ์ด๋ค.
            
    - ์ฃผ์ ๊ธฐ๋ฅ
    
        - ์๊ฒฉ ์๋ฆผ ๋ฉ์์ง ์ ์ก
            
            ex) ์ค์๊ฐ, ์์ฝ
            
        - ๋ค์ํ ๋ฉ์์ง ํ๊ฒํ
            
            ex) ๋จ์ผ ๊ธฐ๊ธฐ, ๊ธฐ๊ธฐ ๊ทธ๋ฃน, ์ฃผ์ ๋ฅผ ๊ตฌ๋ํ ๊ธฐ๊ธฐ
            
        - ๋ฐ์ก ๋ฉ์์ง ์ ์ฅ๊ณผ ๊ด๋ฆฌ
            
            ex) ์๋ฆผ ๋ด์ฉ, ์ํ, ์ต์ข ์ ์ก ์๊ฐ, ์ด๋๋ฅ  ๋ฑ
            
    - ์น ์ฝ์์ ํตํด ์ ์กํ๊ณ  ๊ด๋ฆฌํ๋ค.

<br>
    
### 3. ์๋ฒ ํธ์ ๊ตฌํ
    
4๋จ๊ณ๋ก ์ด๋ค์ง๋ค.
    
1. FCM ์ค์  (Firebase ์ด๊ธฐํ)
2. APNs ๊ตฌ์ฑ
3. Firebase ์ฐ๊ฒฐ
4. Notification ๊ตฌํ
