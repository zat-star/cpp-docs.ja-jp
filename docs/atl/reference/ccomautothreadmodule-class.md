---
title: "CComAutoThreadModule クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アパートメント モデルのモジュール"
  - "CComAutoThreadModule クラス"
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComAutoThreadModule クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL 7.0 では、`CComAutoThreadModule` は互換性のために残されています: [ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md) を詳細については、" "を参照してください。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
class ThreadAllocator= CComSimpleThreadAllocator   
>  
class CComAutoThreadModule :  
public CComModule  
```  
  
#### パラメーター  
 `ThreadAllocator`  
 \[出力\]クラスの管理のスレッドの選択。  既定値は [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)です。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CreateInstance](../Topic/CComAutoThreadModule::CreateInstance.md)|スレッドを選択し、関連付けられているアパートメントのオブジェクトを作成します。|  
|[GetDefaultThreads](../Topic/CComAutoThreadModule::GetDefaultThreads.md)|\(静的\) 動的にプロセッサ数に基づいてモジュールのスレッド数を計算します。|  
|[Init](../Topic/CComAutoThreadModule::Init.md)|モジュールのスレッドを作成します。|  
|[ロック](../Topic/CComAutoThreadModule::Lock.md)|モジュールと現在のスレッドのロック カウントをインクリメントします。|  
|[ロックの解除](../Topic/CComAutoThreadModule::Unlock.md)|モジュールと現在のスレッドのロック カウントをデクリメントします。|  
  
### データ メンバー  
  
### データ メンバー  
  
|||  
|-|-|  
|[dwThreadID](../Topic/CComAutoThreadModule::dwThreadID.md)|現在のスレッド識別子が含まれます。|  
|[m\_Allocator](../Topic/CComAutoThreadModule::m_Allocator.md)|管理のスレッドの選択。|  
|[m\_nThreads](../Topic/CComAutoThreadModule::m_nThreads.md)|モジュールでスレッド数が含まれます。|  
|[m\_pApartments](../Topic/CComAutoThreadModule::m_pApartments.md)|モジュールのアパートメントを管理します。|  
  
## 解説  
  
> [!NOTE]
>  このクラスは、互換性のために [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) と [CAtlModule](../../atl/reference/catlmodule-class.md) の派生クラスに置き換えられます。  次の情報は、ATL の旧リリースで使用するためです。  
  
 `CComAutoThreadModule` は [CComModule](../../atl/reference/ccommodule-class.md) から EXE および Windows サービスの、スレッドがプールされているアパートメント モデル COM サーバーを実装するために取得します。  `CComAutoThreadModule` は、モジュールの各スレッドのアパートメントの管理に [CComApartment](../../atl/reference/ccomapartment-class.md) を使用します。  
  
 複数のアパートメントにオブジェクトを作成するときは、`CComAutoThreadModule` からモジュールを派生します。  また、オブジェクトのクラス定義にクラス ファクトリとして [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) を指定するに [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) のマクロを含める必要があります。  
  
 既定では、ATL COM AppWizard \(Visual Studio .NET の ATL プロジェクト ウィザード\) は `CComModule`から、モジュールを取得します。  `CComAutoThreadModule`を使用するには、クラス定義を変更します。  例:  
  
 [!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/CPP/ccomautothreadmodule-class_1.cpp)]  
  
## 継承階層  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../Topic/ATL%20Module%20Classes.md)