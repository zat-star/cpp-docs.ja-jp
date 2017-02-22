---
title: "CAtlComModule クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlComModule"
  - "CAtlComModule"
  - "ATL::CAtlComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlComModule クラス"
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlComModule クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、COM サーバー モジュールを実装します。  
  
## 構文  
  
```  
  
   class CAtlComModule :  
public _ATL_COM_MODULE  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlComModule::CAtlComModule](../Topic/CAtlComModule::CAtlComModule.md)|コンストラクターです。|  
|[CAtlComModule::~CAtlComModule](../Topic/CAtlComModule::~CAtlComModule.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlComModule::RegisterServer](../Topic/CAtlComModule::RegisterServer.md)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新するときにこのメソッドを呼び出します。|  
|[CAtlComModule::RegisterTypeLib](../Topic/CAtlComModule::RegisterTypeLib.md)|タイプ ライブラリを登録するためにこのメソッドを呼び出します。|  
|[CAtlComModule::UnregisterServer](../Topic/CAtlComModule::UnregisterServer.md)|登録にこのメソッドをオブジェクト マップ内の各オブジェクトで呼び出します。|  
|[CAtlComModule::UnRegisterTypeLib](../Topic/CAtlComModule::UnRegisterTypeLib.md)|登録に、タイプ ライブラリにこのメソッドを呼び出します。|  
  
## 解説  
 `CAtlComModule` は、COM サーバー モジュールを実装して、モジュールのコンポーネントにアクセスできるようにクライアントができます。  
  
 このクラスは、ATL の以前のバージョンで使用されて [CComModule](../../atl/reference/ccommodule-class.md) に残されているクラスを置き換えます。  [ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md) を詳細については、" "を参照してください。  
  
## 継承階層  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)  
  
 `CAtlComModule`  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)   
 [クラスの概要](../../atl/atl-class-overview.md)