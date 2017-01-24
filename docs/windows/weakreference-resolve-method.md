---
title: "WeakReference::Resolve メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::Resolve"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Resolve メソッド"
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference::Resolve メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
#### パラメーター  
 `riid`  
 インターフェイス ID  
  
 `ppvObject`  
 この操作が完了すると、強い参照カウントが 0 以外のは現在の強い参照のコピー。  
  
## 戻り値  
  
-   この操作が正常に終了した場合、強い参照カウントがゼロでは S\_OK を返します。  `ppvObject` パラメーターに `nullptr` が設定されています。  
  
-   この操作が正常に終了した場合、強い参照カウントは 0 以外の S\_OK です。  `ppvObject` パラメーターは、強い参照に設定されます。  
  
-   この操作は、原因を示す HRESULT に失敗しました。  
  
## 解説  
 強い参照カウントが 0 以外のは現在の強い参照値に指定したポインターを設定します。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [WeakReference クラス](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)