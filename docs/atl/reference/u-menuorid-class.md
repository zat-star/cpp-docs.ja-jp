---
title: "_U_MENUorID クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL._U_MENUorID"
  - "ATL::_U_MENUorID"
  - "_U_MENUorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_MENUorID クラス"
  - "U_MENUorID クラス"
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# _U_MENUorID クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、**CreateWindow** と **CreateWindowEx** のラッパー クラスが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class _U_MENUorID  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[\_U\_MENUorID::\_U\_MENUorID](../Topic/_U_MENUorID::_U_MENUorID.md)|コンストラクターです。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[\_U\_MENUorID::m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md)|メニューへのハンドルです。|  
  
## 解説  
 この引数アダプター クラスによって、呼び出し元側で明示的なキャストを使用せずに、関数に渡される ID \(**uint**\) またはメニュー ハンドル \(`HMENU`\) ができます。  
  
 このクラスは、メニュー ハンドルはなく、子ウィンドウ ID \(**uint**\) の可能性がある `HMENU` の引数を受け取る Windows API、特に [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) と [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) の関数のラッパーを実行するようにデザインされています。  たとえば、[CWindowImpl::Create](../Topic/CWindowImpl::Create.md)にパラメーターとして使用中のこのクラスを確認できます。  
  
 クラスは 2 種類のコンストラクター オーバーロードを定義します: 1 つが **uint** の引数を受け取り、そのほかのは `HMENU` の引数を受け取ります。  **uint** の引数は、クラスの一つのデータ メンバー、[m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md)に格納されているコンストラクターと結果の `HMENU` に、キャストします。  `HMENU` のコンストラクターへの引数は変換されずに格納されます。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)