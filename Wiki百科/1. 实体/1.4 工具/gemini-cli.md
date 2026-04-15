---
title: gemini-cli
updated: 2026-04-15
type: entity
category: tools
official: true
developer: Google
language: TypeScript/JavaScript
license: Apache-2.0
repo: https://github.com/google-gemini/gemini-cli
npm: https://www.npmjs.com/package/@google/gemini-cli
docs: https://github.com/google-gemini/gemini-cli
install:
  - npm install -g @google/gemini-cli
  - 版本: 0.37.1
  - 验证: gemini --version
related:
  - [[Gemini]]
  - [[Google AI Studio]]
  - [[Wiki百科/2. 主题/2.3 方法论/Prompt Engineering.md]]
  - [[prompts.chat]]
---

# gemini-cli

Google 官方发布的 Gemini 命令行客户端，支持与 Gemini 模型交互、文件上传以及 MCP 服务管理等能力。
## 瀹夎

```bash
npm install -g @google/gemini-cli
gemini --version  # 楠岃瘉瀹夎
```

**鐗堟湰:** 0.37.1锛堟埅鑷?2026-04 璁板綍锛?
## 璁よ瘉鏂瑰紡

gemini-cli 鏀寔涓ょ璁よ瘉鏂瑰紡锛屾牴鎹娇鐢ㄧ幆澧冮€夋嫨锛?
### 鏂瑰紡涓€锛欰PI Key锛堟帹鑽愮敤浜庢湇鍔″櫒/鏃犳祻瑙堝櫒鐜锛?
1. 璁块棶 [Google AI Studio API Key 椤甸潰](https://aistudio.google.com/apikey)
2. 鍒涘缓 API 瀵嗛挜
3. 璁剧疆鐜鍙橀噺锛?
```bash
export GEMINI_API_KEY=浣犵殑API瀵嗛挜
```

4. 杩愯 `gemini` 鍗冲彲浣跨敤

**浼樼偣锛?* 鏃犻渶娴忚鍣紝閫傚悎 CI/CD銆佹湇鍔″櫒銆佸鍣ㄧ幆澧冦€?
### 鏂瑰紡浜岋細OAuth锛堥€傜敤浜庢湰鍦版闈㈢幆澧冿級

gemini-cli 浣跨敤 Google OAuth 2.0 杩涜韬唤楠岃瘉锛?
- **OAuth 瀹㈡埛绔?ID:** `681255809395-oo8ft2oprdrnp9e3aqf6av3hmdib135j.apps.googleusercontent.com`
- **鎺堟潈鑼冨洿:** `https://www.googleapis.com/auth/cloud-platform`
- **鍥炶皟鍦板潃:** `http://127.0.0.1:{闅忔満绔彛}/oauth2callback`
- **娴佺▼:**
  1. CLI 鍚姩鏈湴 HTTP 鏈嶅姟鍣紙闅忔満绔彛锛?  2. 鐢熸垚 OAuth URL 骞跺湪娴忚鍣ㄤ腑鎵撳紑
  3. 鐢ㄦ埛鎺堟潈鍚庯紝Google 閲嶅畾鍚戝埌鏈湴鍥炶皟
  4. 鏈嶅姟鍣ㄦ崟鑾锋巿鏉冪爜锛屼氦鎹㈣闂护鐗?  5. 浠ょ墝淇濆瓨鍦ㄦ湰鍦帮紙鍔犲瘑瀛樺偍锛?
**闄愬埗锛?* 闇€瑕佸浘褰㈢晫闈㈡祻瑙堝櫒锛屽湪鏃犵晫闈㈢殑鏈嶅姟鍣ㄧ幆澧冩棤娉曞畬鎴愩€?
#### OAuth 鐜鍙橀噺

- `NO_BROWSER=true` 鈥?绂佺敤鑷姩鎵撳紑娴忚鍣紝URL 浼氭墦鍗板埌杈撳嚭涓紙浣嗕粛闇€鎵嬪姩瀹屾垚鍥炶皟锛屼笉鎺ㄨ崘锛?- `OAUTH_CALLBACK_HOST` 鈥?鍥炶皟鏈嶅姟鍣ㄧ洃鍚湴鍧€锛岄粯璁?`127.0.0.1`
- `OAUTH_CALLBACK_PORT` 鈥?鎸囧畾鍥炶皟绔彛锛堥粯璁ら殢鏈洪€夋嫨鍙敤绔彛锛?
#### 涓轰綍 OAuth 涓嶉€傜敤浜庢湇鍔″櫒

鍦ㄦ棤鍥惧舰鐣岄潰鐨?Linux 鏈嶅姟鍣ㄧ幆澧冿細
- 鏃犳硶鑷姩鎵撳紑娴忚鍣?- 鍗充娇鎵嬪姩澶嶅埗 URL 鎺堟潈锛屾湰鍦板洖璋冩湇鍔″櫒浠嶅湪杩愯锛屼絾鐢ㄦ埛鏃犳硶杞绘槗瀹屾垚 OAuth 娴佺▼鐨勪氦浜?- 瀹樻柟鎺ㄨ崘浣跨敤 API Key

## 閰嶇疆

閰嶇疆鏂囦欢浣嶇疆锛歚~/.gemini/settings.json`

绀轰緥閰嶇疆锛?
```json
{
  "model": {
    "provider": "google-genai",
    "model": "gemini-2.5-pro"
  }
}
```

**娉ㄦ剰锛?* `model` 瀛楁蹇呴』涓哄璞℃牸寮忥紙鍖呭惈 `provider` 鍜?`model`锛夛紝瀛楃涓叉牸寮忎細瀵艰嚧閿欒銆?
## 鍩烘湰浣跨敤

```bash
# 浜や簰妯″紡锛堝惎鍔ㄥ悗杈撳叆闂锛?gemini

# 鍗曟鏌ヨ
gemini "瑙ｉ噴浠€涔堟槸閲忓瓙璁＄畻"

# 涓婁紶鏂囦欢骞舵彁闂?gemini -f document.pdf "鎬荤粨杩欎唤鏂囨。"

# 鎸囧畾妯″瀷
gemini --model gemini-2.0-flash "浣犵殑闂"
```

## 鍔熻兘鐗规€?
- **浜や簰寮忓璇?** 榛樿鍚姩 REPL 妯″紡锛屾敮鎸佸杞璇?- **鏂囦欢涓婁紶:** 鏀寔 PDF銆佸浘鐗囥€佹枃鏈瓑澶氱鏍煎紡
- **MCP 鏈嶅姟鍣ㄧ鐞?** `gemini mcp` 瀛愬懡浠ゆ坊鍔犮€佺鐞?MCP 鏈嶅姟
- **鎵╁睍绯荤粺:** 鏀寔瀹夎绀惧尯鎵╁睍锛坋xtensions锛?- **鎶€鑳斤紙Skills锛?** 绠＄悊鍜屼娇鐢ㄨ嚜瀹氫箟鎶€鑳?- **閽╁瓙锛圚ooks锛?** 鑷畾涔夊懡浠ゅ拰鑷姩鍖?- **澶氭ā鎬?** 鏀寔鍥惧儚銆侀煶棰戙€佽棰戣緭鍏?
## 涓?Wiki 绯荤粺鐨勯泦鎴?
鏈煡璇嗗簱宸插皢 gemini-cli 绾冲叆绠＄悊锛?
- **瀹炰綋椤甸潰:** [[Wiki鐧剧/1. 瀹炰綋/1.4 宸ュ叿/gemini-cli.md]]锛堟湰椤碉級
- **涓婚椤甸潰:** [[Gemini]] 鈥?妯″瀷绯诲垪銆佽兘鍔涙杩?- **鍘熷璧勬枡:** [[Wiki鐧剧/3. 鍘熷鏉ユ簮/涔︾睄/gemini-cli-README.md]]
- **鐩稿叧宸ュ叿:** [[Wiki鐧剧/1. 瀹炰綋/1.5 椤圭洰/prompts.chat.md|prompts.chat]] 鈥?Prompt 宸ョ▼璧勬簮

## 鏁呴殰鎺掓煡

### 璁よ瘉澶辫触

- 纭 `GEMINI_API_KEY` 宸叉纭缃細`echo $GEMINI_API_KEY`
- API Key 闇€浠?[Google AI Studio](https://aistudio.google.com/apikey) 鑾峰彇
- 鑻ヤ娇鐢?OAuth锛岀‘淇濇湰鍦扮鍙ｆ湭琚崰鐢紝涓斿彲璁块棶 `127.0.0.1`

### 鏃犳硶鎵撳紑娴忚鍣?
- 璁剧疆 `NO_BROWSER=true` 鏌ョ湅鎵撳嵃鐨?URL
- 鍦ㄦ湇鍔″櫒鐜锛岀洿鎺ヤ娇鐢?API Key 璁よ瘉

### 閰嶇疆鏂囦欢閿欒

- 妫€鏌?`~/.gemini/settings.json` 鏍煎紡
- 纭繚 `model` 涓哄璞★細`{"provider":"google-genai","model":"gemini-2.5-pro"}`

## 鏇存柊鏃ュ織

- **2026-04-12** 瀹夎 gemini-cli 0.37.1锛屽垱寤烘湰椤甸潰锛岃褰?OAuth 鍒嗘瀽鍜?API Key 鎺ㄨ崘鏂规

## 寰呭姙浠诲姟

- [ ] 瀹炴祴 API Key 璁よ瘉娴佺▼
- [ ] 褰曞埗 gemini-cli 浣跨敤绀轰緥瑙嗛
- [ ] 鏁寸悊甯哥敤 Prompt 妯℃澘鍒?[[Wiki鐧剧/2. 涓婚/2.3 鏂规硶璁?Prompt Engineering.md]]

