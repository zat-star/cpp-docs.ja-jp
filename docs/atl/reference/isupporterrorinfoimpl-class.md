---
title: "ISupportErrorInfoImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::ISupportErrorInfoImpl<piid>"
  - "ATL::ISupportErrorInfoImpl"
  - "ISupportErrorInfoImpl"
  - "ATL.ISupportErrorInfoImpl<piid>"
  - "ATL.ISupportErrorInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "エラー情報, ATL"
  - "ISupportErrorInfo ATL の実装"
  - "ISupportErrorInfoImpl クラス"
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ISupportErrorInfoImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、一つのインターフェイスだけがオブジェクトでエラーを生成するとき [ISupportErrorInfo Interface](http://msdn.microsoft.com/ja-jp/42d33066-36b4-4a5b-aa5d-46682e560f32) の既定の実装を提供し、使用できます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
const IID* piid   
>  
class ATL_NO_VTABLE ISupportErrorInfoImpl :  
public ISupportErrorInfo  
```  
  
#### パラメーター  
 `piid`  
 このインターフェイスの IID へのポインターが [IErrorInfo](http://msdn.microsoft.com/ja-jp/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)をサポートします。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](../Topic/ISupportErrorInfoImpl::InterfaceSupportsErrorInfo.md)|`riid` によって識別されるインターフェイスが [IErrorInfo](http://msdn.microsoft.com/ja-jp/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) のインターフェイスをサポートしているかどうかを示します。|  
  
## 解説  
 [ISupportErrorInfo Interface](http://msdn.microsoft.com/ja-jp/42d33066-36b4-4a5b-aa5d-46682e560f32) はエラー情報がクライアントに返すことができるようになります。  **IErrorInfo** を使用するオブジェクトは **\[ISupportErrorInfo\]**を実装する必要があります。  
  
 一つのインターフェイスだけがオブジェクトでエラーを生成するとき `ISupportErrorInfoImpl` クラスは **\[ISupportErrorInfo\]** の既定の実装を提供し、使用できます。  以下はその例です。  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/CPP/isupporterrorinfoimpl-class_1.h)]  
  
## 継承階層  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)