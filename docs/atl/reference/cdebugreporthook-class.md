---
title: "CDebugReportHook クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CDebugReportHook"
  - "CDebugReportHook"
  - "ATL::CDebugReportHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDebugReportHook クラス"
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDebugReportHook クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、名前付きパイプにデバッグ レポートを送信するために使用します。  
  
## 構文  
  
```  
  
class CDebugReportHook  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDebugReportHook::CDebugReportHook](../Topic/CDebugReportHook::CDebugReportHook.md)|呼び出し [SetPipeName](../Topic/CDebugReportHook::SetPipeName.md)、[SetTimeout](../Topic/CDebugReportHook::SetTimeout.md)と [SetHook](../Topic/CDebugReportHook::SetHook.md)。|  
|[CDebugReportHook::~CDebugReportHook](../Topic/CDebugReportHook::~CDebugReportHook.md)|呼び出し [CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md)。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDebugReportHook::CDebugReportHookProc](../Topic/CDebugReportHook::CDebugReportHookProc.md)|\(静的\) C ランタイムのデバッグのレポートのプロセスにフック カスタム レポート関数。|  
|[CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md)|名前付きパイプにデバッグ レポートを送信するが停止し、前のレポート用のフックを復元するには、このメソッドを呼び出します。|  
|[CDebugReportHook::SetHook](../Topic/CDebugReportHook::SetHook.md)|名前付きパイプにデバッグ レポートの送信を呼び出すには、このメソッドを呼び出します。|  
|[CDebugReportHook::SetPipeName](../Topic/CDebugReportHook::SetPipeName.md)|デバッグ レポートが送信されるパイプのコンピューターと名前を設定するには、このメソッドを呼び出します。|  
|[CDebugReportHook::SetTimeout](../Topic/CDebugReportHook::SetTimeout.md)|このクラスを使用するには、名前付きパイプを待機する時間をミリ秒単位で設定するには、このメソッドを呼び出します。|  
  
## 解説  
 名前付きパイプにデバッグ レポートを送信するようにサービスまたはアプリケーションのデバッグ ビルドでこのクラスのインスタンスを作成します。  デバッグ レポートは [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) を呼び出すか、[ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md) と [ATLASSERT](../Topic/ATLASSERT.md) のマクロのように、この関数のラッパーを使用して生成されます。  
  
 このクラスは相互に [ウィンドウの場所](http://msdn.microsoft.com/library/windows/desktop/ms687096)非対話形式で実行されるコンポーネントをデバッグできるようにします。  
  
 デバッグ レポートが基になるスレッドのセキュリティ コンテキストを使用して送信されることに注意してください。  偽装は一時的にデバッグ レポートが最小特権のユーザーの偽装が発生している Web アプリケーションのような状態で表示できるように無効になります。  
  
## 必要条件  
 **Header:** atlutil.h  
  
## 参照  
 [クラス](../../atl/reference/atl-classes.md)