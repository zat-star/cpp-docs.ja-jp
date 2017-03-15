---
title: "HStringReference クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HStringReference クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既存の文字列から作成された HSTRING を表します。  
  
## 構文  
  
```cpp  
class HStringReference;  
```  
  
## 解説  
 新しい HSTRING のバッキング バッファーの有効期間は [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]では管理されていません。  呼び出し元はソース文字列をスタック フレームに割り当てることで、ヒープ割り当てを回避し、メモリ リークのリスクを排除します。  また、呼び出し元はアタッチ済みの HSTRING の有効期間中にソース文字列が変更されないことを確認する必要があります。  詳細については、「[WindowsCreateStringReference function](http://msdn.microsoft.com/ja-jp/0361bb7e-da49-4289-a93e-de7aab8712ac)」を参照してください。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[HStringReference::HStringReference コンストラクター](../windows/hstringreference-hstringreference-constructor.md)|HStringReference クラスの新しいインスタンスを初期化します。|  
  
### メンバー  
  
|メンバー|説明|  
|----------|--------|  
|[HStringReference::CopyTo メソッド](../windows/hstringreference-copyto-method.md)|現在の HStringReference オブジェクトを HSTRING オブジェクトにコピーします。|  
|[HStringReference::Get メソッド](../windows/hstringreference-get-method.md)|基になる HSTRING ハンドルの値を取得します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[HStringReference::Operator\= 演算子](../windows/hstringreference-operator-assign-operator.md)|別の HStringReference オブジェクトの値を現在の HStringReference オブジェクトに移動します。|  
|[HStringReference::Operator\=\= 演算子](../windows/hstringreference-operator-equality-operator.md)|2 つのパラメーターが等しいかどうかを示します。|  
|[HStringReference::Operator\!\= 演算子](../windows/hstringreference-operator-inequality-operator.md)|2 つのパラメーターが異なるかどうかを示します。|  
  
## 継承階層  
 `HStringReference`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [Microsoft::WRL::Wrappers 名前空間](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)