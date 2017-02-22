---
title: "_U_RECT クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::_U_RECT"
  - "_U_RECT"
  - "ATL._U_RECT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_RECT クラス"
  - "U_RECT クラス"
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# _U_RECT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この引数アダプター クラスによって、ポインターとして実装される関数に `RECT` ポインターまたは参照を渡すことができます。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class _U_RECT  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[\_U\_RECT::\_U\_RECT](../Topic/_U_RECT::_U_RECT.md)|コンストラクターです。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[\_U\_RECT::m\_lpRect](../Topic/_U_RECT::m_lpRect.md)|`RECT`へのポインター。|  
  
## 解説  
 クラスは 2 種類のコンストラクター オーバーロードを定義します: 1 つが **RECT&** の引数を受け取り、そのほかのは `LPRECT` の引数を受け取ります。  一つ目のコンストラクターは、クラスの一つのデータ メンバー、[m\_lpRect](../Topic/_U_RECT::m_lpRect.md)で参照引数のアドレスを格納します。  ポインターのコンストラクターへの引数は変換されずに格納されます。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)