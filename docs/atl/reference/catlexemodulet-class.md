---
title: "CAtlExeModuleT クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlExeModuleT<T>"
  - "CAtlExeModuleT"
  - "ATL.CAtlExeModuleT<T>"
  - "ATL::CAtlExeModuleT"
  - "ATL.CAtlExeModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlExeModuleT クラス"
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlExeModuleT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、アプリケーション用のモジュールを表します。  
  
## 構文  
  
```  
  
      template <  
   class T   
>  
class ATL_NO_VTABLE CAtlExeModuleT :  
   public CAtlModuleT< T >  
```  
  
#### パラメーター  
 `T`  
 `CAtlExeModuleT`から派生したクラス。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlExeModuleT::CAtlExeModuleT](../Topic/CAtlExeModuleT::CAtlExeModuleT.md)|コンストラクターです。|  
|[CAtlExeModuleT::~CAtlExeModuleT](../Topic/CAtlExeModuleT::~CAtlExeModuleT.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlExeModuleT::InitializeCom](../Topic/CAtlExeModuleT::InitializeCom.md)|COM の初期化。|  
|[CAtlExeModuleT::ParseCommandLine](../Topic/CAtlExeModuleT::ParseCommandLine.md)|コマンド ラインを分析し、登録を必要に応じて実行します。|  
|[CAtlExeModuleT::PostMessageLoop](../Topic/CAtlExeModuleT::PostMessageLoop.md)|このメソッドは、メッセージ ループが終了した直後に呼び出されます。|  
|[CAtlExeModuleT::PreMessageLoop](../Topic/CAtlExeModuleT::PreMessageLoop.md)|このメソッドは、メッセージ ループに入る直前に呼び出されます。|  
|[CAtlExeModuleT::RegisterClassObjects](../Topic/CAtlExeModuleT::RegisterClassObjects.md)|クラス オブジェクトを登録します。|  
|[CAtlExeModuleT::RevokeClassObjects](../Topic/CAtlExeModuleT::RevokeClassObjects.md)|クラス オブジェクトを取り消します。|  
|[CAtlExeModuleT::Run](../Topic/CAtlExeModuleT::Run.md)|このメソッドは初期化するために EXE モジュールのコードを実行してメッセージ ループを実行する方法、およびクリーンアップされます。|  
|[CAtlExeModuleT::RunMessageLoop](../Topic/CAtlExeModuleT::RunMessageLoop.md)|このメソッドは、メッセージ ループを実装します。|  
|[CAtlExeModuleT::UninitializeCom](../Topic/CAtlExeModuleT::UninitializeCom.md)|COM の状態に戻します。|  
|[CAtlExeModuleT::Unlock](../Topic/CAtlExeModuleT::Unlock.md)|モジュールのロック カウントをデクリメントします。|  
|[CAtlExeModuleT::WinMain](../Topic/CAtlExeModuleT::WinMain.md)|このメソッドは、EXE を実行するために必要なコードを実装します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md)|そこでモジュールをシャットダウン遅延することを表すフラグです。|  
|[CAtlExeModuleT::m\_dwPause](../Topic/CAtlExeModuleT::m_dwPause.md)|すべてのオブジェクトを確認するために使用される一時停止の値がシャットダウン前に解放されます。|  
|[CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md)|モジュールのアンロードを遅延させるために使用されるタイムアウト値。|  
  
## 解説  
 `CAtlExeModuleT` は、アプリケーション \(EXE\) でモジュールを表し、EXE を作成し、コマンド ラインを処理し、クラス オブジェクトを登録し、メッセージ ループの実行、および終了のクリーンをサポートするコードが含まれています。  
  
 このクラスは、EXE サーバーの COM オブジェクトが連続的に作成され、破棄するとパフォーマンスが向上するようにデザインされています。  最後の COM オブジェクトが解放された後、EXE は [CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md) データ メンバーを指定する期間を待機します。  アクティビティがこの期間中に \(つまり、COM オブジェクトは作成されません\) 場合、シャットダウン処理が開始されます。  
  
 [CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md) のデータ メンバーは EXE を配置前に定義した機構を使用するかどうかを確認するために使用されるフラグです。  これが false に設定されている場合、モジュールは直ちに終了します。  
  
 ATL モジュールの詳細については、[ATL モジュール クラス](../Topic/ATL%20Module%20Classes.md)を参照してください。  
  
## 継承階層  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [ATLDuck サンプル](../../top/visual-cpp-samples.md)   
 [CAtlModuleT クラス](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT クラス](../../atl/reference/catldllmodulet-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)