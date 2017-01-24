---
title: "DeferrableEventArgs::GetDeferral メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DeferrableEventArgs::GetDeferral メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

遅延イベントを表す [遅延Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) オブジェクトへの参照を取得します。  
  
## 構文  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### パラメーター  
 `result`  
 呼び出しが完了したときに [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) オブジェクトを参照するポインター。  
  
## 戻り値  
 成功した場合は S\_OK、そうでない場合はエラーを示す HRESULT。  
  
## 解説  
 コード例は、[DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)