---
title: "CAtlAutoThreadModule クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlAutoThreadModule"
  - "CAtlAutoThreadModule"
  - "ATL::CAtlAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModule クラス"
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlAutoThreadModule クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、スレッドがプールされているアパートメント モデル COM サーバーを実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      class CAtlAutoThreadModule :  
public CAtlAutoThreadModuleT< CAtlAutoThreadModule >  
```  
  
## 解説  
 `CAtlAutoThreadModule` は [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) から派生し、スレッドのプールされているアパートメント モデル COM サーバーを実装します。  `CAtlAutoThreadModule` は、モジュールの各スレッドのアパートメントの管理に [CComApartment](../../atl/reference/ccomapartment-class.md) を使用します。  
  
 では、オブジェクトのクラス定義のクラス ファクトリとして [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) を指定するに [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) のマクロを使用する必要があります。  次 `CAtlAutoThreadModule`などの `CAtlAutoThreadModuleT` から派生したクラスのインスタンスを追加する必要があります。  例:  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  このクラスは [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) に残されているクラスを置き換えます。  
  
## 継承階層  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [CAtlAutoThreadModuleT クラス](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../Topic/ATL%20Module%20Classes.md)