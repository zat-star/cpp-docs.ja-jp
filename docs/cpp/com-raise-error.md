---
title: "_com_raise_error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_raise_error 関数"
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# _com_raise_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 失敗に応答して [\_com\_error](../cpp/com-error-class.md) をスローします。  
  
## 構文  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### パラメーター  
 `hr`  
 `HRESULT` 情報。  
  
 `perrinfo`  
 **IErrorInfo** オブジェクト。  
  
## 解説  
 `_com_raise_error` は、comdef.h で定義され、同じ名前とプロトタイプのユーザー作成のバージョンで置き換えることができます。  `#import` を使用し、C\+\+ 例外処理を使用しない場合は、こうすることができます。  その場合、**\_com\_raise\_error** のユーザー バージョンが `longjmp` を実行するか、メッセージ ボックスを表示して停止するかを決定することがあります。  ユーザー バージョンで返すことはできません。コンパイラ COM サポート コードがそれを予期していないためです。  
  
 また、[\_set\_com\_error\_handler](../cpp/set-com-error-handler.md) を使用して、既定のエラー処理関数を置き換えることもできます。  
  
 既定では、`_com_raise_error` は次のように定義されています。  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
## END Microsoft 固有の仕様  
  
## 必要条件  
 **ヘッダー:** comdef.h  
  
 **Lib:** "wchar\_t をネイティブ型として認識" のコンパイラ オプションが有効な場合は、comsuppw.lib または comsuppwd.lib を使用します。  "wchar\_t をネイティブ型として認識" の設定が無効になっている場合は、comsupp.lib を使用します。  詳細については、「[\/Zc:wchar\_t \(wchar\_t をネイティブ型として認識\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。  
  
## 参照  
 [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)   
 [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)