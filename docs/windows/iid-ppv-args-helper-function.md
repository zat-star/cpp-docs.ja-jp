---
title: "IID_PPV_ARGS_Helper 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/IID_PPV_ARGS_Helper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IID_PPV_ARGS_Helper 関数"
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IID_PPV_ARGS_Helper 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定された引数の型が `IUnknown` インターフェイスから派生することを確認します。  
  
> [!IMPORTANT]
>  このテンプレートの特殊化を WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  代わりに使用 [IID\_PPV\_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) します。  
  
## 構文  
  
```  
template<  
   typename T  
>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### パラメーター  
 `T`  
 `pp`引数の型。  
  
 `pp`  
 二重の間接参照ポインター。  
  
## 戻り値  
 引数 `pp` は `void`へのポインターへのポインターにキャストしました。  
  
## 解説  
 コンパイル時のエラーは、テンプレート パラメーター `T` が `IUnknown`から派生しなければ生成されます。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
## 参照  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ja-jp/00000000-0000-0000-0000-000000000000)