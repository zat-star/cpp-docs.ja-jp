---
title: "Platform::ArrayReference クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ArrayReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ArrayReference クラス"
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ArrayReference クラス
`ArrayReference` は、C スタイル配列に入力データを格納するときに、入力パラメーターの [Platform::Array^](../cppcx/platform-array-class.md) と置き換えることができる最適化の種類です。  
  
## 構文  
  
```vb  
  
```  
  
```csharp  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[ArrayReference::ArrayReference コンストラクター](../cppcx/arrayreference-arrayreference-constructor.md)|`ArrayReference` クラスの新しいインスタンスを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[ArrayReference::operator\(\) 演算子](../cppcx/arrayreference-operator-call-operator.md)|この `ArrayReference` を `Platform::Array<T>^*` に変換します。|  
|[ArrayReference::operator\= 演算子](../cppcx/arrayreference-operator-assign-operator.md)|このインスタンスに別の `ArrayReference` の内容を割り当てます。|  
  
## 例外  
  
## 解説  
 `ArrayReference` を使用して C スタイル配列にデータを格納する方法であれば、一度 `Platform::Array` 変数にコピーしたうえで改めて C スタイル配列にコピーするような余分な操作が不要になります。`ArrayReference` を使用した場合には、コピー操作が 1 回のみとなります。 コード例については、「[Array と WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)」を参照してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  
  
## サブセクションの見出し  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)