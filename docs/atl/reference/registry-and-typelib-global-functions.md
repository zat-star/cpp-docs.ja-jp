---
title: "レジストリとタイプ ライブラリに関するグローバル関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegistryDataExchange 関数, グローバル関数"
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# レジストリとタイプ ライブラリに関するグローバル関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の関数は、タイプ ライブラリの読み込みと登録をサポートします。  
  
> [!IMPORTANT]
>  次の表に示す関数は [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](../Topic/AtlRegisterTypeLib.md)|この関数は、タイプ ライブラリを登録するために呼び出されます。|  
|[AtlUnRegisterTypeLib](../Topic/AtlUnRegisterTypeLib.md)|タイプ ライブラリの登録を解除します。|  
|[AtlLoadTypeLib](../Topic/AtlLoadTypeLib.md)|この関数は、タイプ ライブラリを読み込むために呼び出されます。|  
|[AtlUpdateRegistryFromResourceD](../Topic/AtlUpdateRegistryFromResourceD.md)|この関数は、提供されたリソースのレジストリを更新するために呼び出されます。|  
|[RegistryDataExchange](../Topic/RegistryDataExchange.md)|システム レジストリのデータの読み取り\/書き込みを行います。  [Registry Data Exchange Macros](../../atl/reference/registry-data-exchange-macros.md)によって呼び出されます。|  
  
 これらの関数は、プログラムが情報を格納するためにレジストリ内のどのノードを使用するかを制御します。  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](../Topic/AtlGetPerUserRegistration.md)|アプリケーションがレジストリ アクセスを **HKEY\_CURRENT\_USER** \(**HKCU**\) ノードにリダイレクトするかどうかを取得します。|  
|[AtlSetPerUserRegistration](../Topic/AtlSetPerUserRegistration.md)|アプリケーションがレジストリ アクセスを **HKEY\_CURRENT\_USER** \(**HKCU**\) ノードにリダイレクトするかどうかを設定します。|  
  
## 参照  
 [関数](../../atl/reference/atl-functions.md)