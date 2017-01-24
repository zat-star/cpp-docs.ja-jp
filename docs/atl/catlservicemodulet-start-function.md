---
title: "CAtlServiceModuleT::Start 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule.Start"
  - "CServiceModule::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start メソッド"
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::Start 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次 `CAtlServiceModuleT::Start`を呼び出すサービスが実行されると、**\_tWinMain** は **CAtlServiceModuleT::WinMain**を呼び出します。  
  
 `CAtlServiceModuleT::Start` は起動関数に各サービスをマップする **SERVICE\_TABLE\_ENTRY** の構造体の配列を設定します。  この配列は Win32 API 関数、[StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324)に渡されます。  理論的には、EXE 1 は、複数サービスを処理し、配列は **SERVICE\_TABLE\_ENTRY** の複数の構造を持つことができます。  現在、ATL 生成されたサービスは EXE ごとに 1 回サービスのみが。  したがって、配列に起動関数としてサービス名と **\_ServiceMain** を含む単一エントリがあります。  **\_ServiceMain** は静的でないメンバー関数を呼び出す `CAtlServiceModuleT`、`ServiceMain`の静的メンバー関数です。  
  
> [!NOTE]
>  **StartServiceCtrlDispatcher** のエラーは、Services Control Manager \(SCM\) に接続する、プログラムがサービスとして実行されていないことを意味します。  この場合は、プログラムがローカル サーバーとして実行できるように `CAtlServiceModuleT::Run` を直接呼び出します。  ローカル サーバーとしてプログラムを実行する方法の詳細については、[デバッグのヒント](../atl/debugging-tips.md)を参照してください。  
  
## 参照  
 [サービス](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../Topic/CAtlServiceModuleT::Start.md)