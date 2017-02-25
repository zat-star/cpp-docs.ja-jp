---
title: "CCommandLineInfo クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCommandLineInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーションのフラグ [C++]"
  - "argv 引数"
  - "CCommandLineInfo クラス"
  - "コマンド ライン, 解析"
  - "解析, コマンド ライン引数"
  - "スタートアップ コード, 解析 (コマンド ライン引数を)"
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCommandLineInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーション起動時のコマンド ライン解析を補助します。  
  
## 構文  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CCommandLineInfo::CCommandLineInfo](../Topic/CCommandLineInfo::CCommandLineInfo.md)|既定の `CCommandLineInfo` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CCommandLineInfo::ParseParam](../Topic/CCommandLineInfo::ParseParam.md)|各パラメーターを解析するには、このコールバックをオーバーライドします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md)|コマンド ライン **\/Automation** オプションが見つかったかどうかを示します。|  
|[CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md)|コマンド ライン **\/Embedding** オプションが見つかったかどうかを示します。|  
|[CCommandLineInfo::m\_bShowSplash](../Topic/CCommandLineInfo::m_bShowSplash.md)|スプラッシュ スクリーンを表示するかどうかを示します。|  
|[CCommandLineInfo::m\_nShellCommand](../Topic/CCommandLineInfo::m_nShellCommand.md)|処理されるシェル コマンドを示します。|  
|[CCommandLineInfo::m\_strDriverName](../Topic/CCommandLineInfo::m_strDriverName.md)|シェル コマンドで印刷先が指定された場合に、ドライバー名を示します。それ以外の場合は空です。|  
|[CCommandLineInfo::m\_strFileName](../Topic/CCommandLineInfo::m_strFileName.md)|開かれるファイル名または印刷されるファイル名を示します。シェル コマンドが新規作成または DDE の場合は空です。|  
|[CCommandLineInfo::m\_strPortName](../Topic/CCommandLineInfo::m_strPortName.md)|シェル コマンドで印刷先が指定された場合に、ポート名を示します。それ以外の場合は空です。|  
|[CCommandLineInfo::m\_strPrinterName](../Topic/CCommandLineInfo::m_strPrinterName.md)|シェル コマンドで印刷先が指定された場合に、プリンター名を示します。それ以外の場合は空です。|  
|[CCommandLineInfo::m\_strRestartIdentifier](../Topic/CCommandLineInfo::m_strRestartIdentifier.md)|再起動マネージャーがアプリケーションを再起動した場合に、再起動マネージャーの一意の再起動識別子を示します。|  
  
## 解説  
 MFC アプリケーションは、通常、アプリケーション オブジェクトの [InitInstance](../Topic/CWinApp::InitInstance.md) 関数でこのクラスのローカル インスタンスを作成します。  `CCommandLineInfo` のオブジェクトを塗りつぶすために [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) を繰り返し呼び出すこのオブジェクトは [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)に渡されます。  `CCommandLineInfo` のオブジェクトは [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md) に、コマンド ライン引数とフラグを処理するために渡されます。  
  
 次のコマンド ライン オプションとパラメーターをカプセル化するためにこのオブジェクトを使用する:  
  
|コマンド ライン引数|実行するコマンド|  
|----------------|--------------|  
|*アプリケーション*|新しいファイル。|  
|*アプリケーションの* ファイル名|ファイルを開きます。|  
|*アプリケーション* **\/p** ファイル名|既定のプリンターに印刷ファイル。|  
|*アプリケーション* **\/pt** ファイル名のプリンター ドライバーのポート|指定したプリンターに印刷ファイル。|  
|*アプリケーション* **\/dde**|開始し、またはのコマンドを待機します。|  
|*アプリケーション* **\/Automation**|OLE オートメーション サーバーとして起動します。|  
|*アプリケーション* **\/Embedding**|編集の開始まで OLE 埋め込みアイテム。|  
|*アプリケーション* **\/Register**<br /><br /> *アプリケーション* **\/Regserver**|登録のタスクを実行するアプリケーションに通知します。|  
|*アプリケーション* **\/Unregister**<br /><br /> *アプリケーション* **\/Unregserver**|非登録のタスクを実行するアプリケーションに通知します。|  
  
 そのほかのフラグおよびパラメーター値を処理する `CCommandLineInfo` から新しいクラスを派生します。  新しいフラグを処理 [ParseParam](../Topic/CCommandLineInfo::ParseParam.md) オーバーライドします。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CCommandLineInfo`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)   
 [CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)