---
title: "WeakReference::Resolve メソッド (プラットフォーム名前空間) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::Resolve"
ms.assetid: 78bbcadd-89d0-4863-a4e8-1d84040eed7d
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::Resolve メソッド (プラットフォーム名前空間)
元の ref クラスへのハンドル、またはオブジェクトが存在しない場合は `nullptr` を返します。  
  
## 構文  
  
```vb  
  
template<typename T>  
T^ Resolve() const  
```  
  
#### パラメーター  
  
## プロパティ値\/戻り値  
 WeakReference オブジェクトが以前関連付けられていた ref クラスへのハンドル、または nullptr。  
  
## 解説  
  
## 使用例  
 コード例の説明です。  
  
```  
  
Bar^ bar = ref new Bar(); //use bar... if (bar != nullptr) { WeakReference wr(bar); Bar^ newReference = wr.Resolve<Bar>(); }  
```  
  
 型パラメーターは、T^ ではなく T であることに注意してください。  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)