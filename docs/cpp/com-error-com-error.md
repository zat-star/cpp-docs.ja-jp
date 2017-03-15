---
title: "_com_error::_com_error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error._com_error"
  - "_com_error::_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error メソッド"
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::_com_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_com_error` オブジェクトを構築します。  
  
## 構文  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### パラメーター  
 `hr`  
 `HRESULT` 情報。  
  
 `perrinfo`  
 **IErrorInfo** オブジェクト。  
  
 **bool fAddRef\=false**  
 コンストラクターが null でない **IErrorInfo** インターフェイスの AddRef を呼び出すようにします。  こうすることで、次の例のように、インターフェイスの所有権が `_com_error` オブジェクトに渡される一般的なケースで参照カウントが正しく実行されます。  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 コードで `_com_error` オブジェクトに所有権を渡さず、`_com_error` デストラクターでの **Release** を相殺するために `AddRef` が必要である場合は、次のようにオブジェクトを構築します。  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 既存の `_com_error` オブジェクト。  
  
## 解説  
 最初のコンストラクターは、`HRESULT` と省略可能な **IErrorInfo** オブジェクトを受け取って新しいオブジェクトを作成します。  2 つ目のコンストラクターは、既存の `_com_error` オブジェクトのコピーを作成します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_error クラス](../cpp/com-error-class.md)