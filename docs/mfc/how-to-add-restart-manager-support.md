---
title: "方法: 再起動マネージャーのサポートを追加する | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "再起動マネージャー"
  - "C++、アプリケーション クラッシュのサポート"
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: 再起動マネージャーのサポートを追加する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

再起動マネージャーは、[!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)] 用の [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] に追加された機能です。 再起動マネージャーにより、アプリケーションが予期せずに終了または再起動した場合のアプリケーションのサポートが強化されます。 再起動マネージャーの動作は、アプリケーションの種類によって異なります。 アプリケーションがドキュメント エディターの場合、再起動マネージャーは、アプリケーションが予期せずに終了したら、開いているドキュメントの状態と内容をアプリケーションが自動的に保存できるようにし、アプリケーションを再起動します。 アプリケーションがドキュメント エディターではない場合、再起動マネージャーは、アプリケーションを再起動しますが、既定ではアプリケーションの状態を保存できません。  
  
 Unicode アプリケーションは、再起動後、タスク ダイアログ ボックスを表示します。 ANSI アプリケーションは、Windows メッセージ ボックスを表示します。 この時点で、ユーザーは自動的に保存されたドキュメントを復元するかどうかを選択します。 自動的に保存されたドキュメントをユーザーが復元しない場合は、再起動マネージャーによって一時ファイルが破棄されます。  
  
> [!NOTE]
>  データの保存とアプリケーションの再起動を行う再起動マネージャーの既定の動作はオーバーライドできます。  
  
 既定では、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] のプロジェクト ウィザードを使用して作成された MFC アプリケーションは、[!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)] を搭載したコンピューターで実行されていれば、再起動マネージャーをサポートします。 アプリケーションが再起動マネージャーをサポートしないようにする場合は、新しいプロジェクト ウィザードで再起動マネージャーを無効にすることができます。  
  
### 既存のアプリケーションが再起動マネージャーをサポートするように設定するには  
  
1.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] で既存の MFC アプリケーションを開きます。  
  
2.  メイン アプリケーションのソース ファイルを開きます。 既定では、これはアプリケーションと同じ名前の .cpp ファイルです。 たとえば、MyProject のメイン アプリケーションのソース ファイルは、MyProject.cpp です。  
  
3.  メイン アプリケーションのコンストラクターを探します。 たとえば、プロジェクトが MyProject である場合、コンストラクターは `CMyProjectApp::CMyProjectApp()` です。  
  
4.  次のコード行をコンストラクターに追加します。  
  
    ```  
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;  
    ```  
  
5.  アプリケーションの `InitInstance` メソッドが、その親の `InitInstance` メソッド \([CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md) または `CWinAppEx::InitInstance`\) を呼び出すことを確認します。`InitInstance` メソッドには、`m_dwRestartManagerSupportFlags` パラメーターをチェックする責任があります。  
  
6.  アプリケーションをコンパイルして実行します。  
  
## 参照  
 [CDataRecoveryHandler クラス](../mfc/reference/cdatarecoveryhandler-class.md)   
 [CWinApp::m\_dwRestartManagerSupportFlags](../Topic/CWinApp::m_dwRestartManagerSupportFlags.md)   
 [CWinApp クラス](../mfc/reference/cwinapp-class.md)   
 [CWinApp::m\_nAutosaveInterval](../Topic/CWinApp::m_nAutosaveInterval.md)   
 [CDocument::OnDocumentEvent](../Topic/CDocument::OnDocumentEvent.md)