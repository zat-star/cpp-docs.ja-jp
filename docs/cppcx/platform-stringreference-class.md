---
title: "Platform::StringReference クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::StringReference クラス
最小のコピー操作で `Platform::String^` 入力パラメーターから他のメソッドに文字列データを渡すために使用できる最適化の手法です。  
  
## 構文  
  
```cpp  
class StringReference  
```  
  
## 解説  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[StringReference::StringReference コンストラクター](../cppcx/stringreference-stringreference-constructor.md)|`StringReference` のインスタンスを作成するための 2 つのコンストラクター。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[StringReference::Data メソッド](../cppcx/stringreference-data-method.md)|文字列データを char16 値の配列として返します。|  
|[StringReference::Length メソッド](../cppcx/stringreference-length-method.md)|文字列内の文字数を返します。|  
|[StringReference::GetHSTRING メソッド](../cppcx/stringreference-gethstring-method.md)|文字列データを HSTRING として返します。|  
|[StringReference::GetString メソッド](../cppcx/stringreference-getstring-method.md)|文字列データを `Platform::String^` として返します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|`StringReference::operator=`|`StringReference` を新しい `StringReference` インスタンスに割り当てます。|  
|`StringReference::operator()`|`StringReference` を `Platform::String^` に変換します。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## 参照  
 [Platform::StringReference Class](../cppcx/platform-stringreference-class.md)