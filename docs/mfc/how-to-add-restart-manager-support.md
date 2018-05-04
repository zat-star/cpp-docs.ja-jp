---
title: '方法: 再起動マネージャーのサポートを追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4550a8a6a6457c4bf5b7acc137a592aa5ecb2e4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-add-restart-manager-support"></a>方法: 再起動マネージャーのサポートを追加する

再起動マネージャーは、Visual Studio for Windows Vista またはそれ以降のオペレーティング システムに追加された機能です。 再起動マネージャーにより、アプリケーションが予期せずに終了または再起動した場合のアプリケーションのサポートが強化されます。 再起動マネージャーの動作は、アプリケーションの種類によって異なります。 アプリケーションがドキュメント エディターの場合、再起動マネージャーは、アプリケーションが予期せずに終了したら、開いているドキュメントの状態と内容をアプリケーションが自動的に保存できるようにし、アプリケーションを再起動します。 アプリケーションがドキュメント エディターではない場合、再起動マネージャーは、アプリケーションを再起動しますが、既定ではアプリケーションの状態を保存できません。  
  
 Unicode アプリケーションは、再起動後、タスク ダイアログ ボックスを表示します。 ANSI アプリケーションは、Windows メッセージ ボックスを表示します。 この時点で、ユーザーは自動的に保存されたドキュメントを復元するかどうかを選択します。 自動的に保存されたドキュメントをユーザーが復元しない場合は、再起動マネージャーによって一時ファイルが破棄されます。  
  
> [!NOTE]
>  データの保存とアプリケーションの再起動を行う再起動マネージャーの既定の動作はオーバーライドできます。  
  
 既定では、プロジェクト ウィザードを使用して作成された MFC アプリケーション[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]アプリケーションは、Windows Vista またはそれ以降のオペレーティング システムをあるコンピューター上で実行されている場合は、再起動マネージャーをサポートします。 アプリケーションが再起動マネージャーをサポートしないようにする場合は、新しいプロジェクト ウィザードで再起動マネージャーを無効にすることができます。  
  
### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>既存のアプリケーションが再起動マネージャーをサポートするように設定するには  
  
1.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]で既存の MFC アプリケーションを開きます。  
  
2.  メイン アプリケーションのソース ファイルを開きます。 既定では、これはアプリケーションと同じ名前の .cpp ファイルです。 たとえば、MyProject のメイン アプリケーションのソース ファイルは、MyProject.cpp です。  
  
3.  メイン アプリケーションのコンストラクターを探します。 たとえば、プロジェクトが MyProject である場合、コンストラクターは `CMyProjectApp::CMyProjectApp()`です。  
  
4.  次のコード行をコンストラクターに追加します。  
  
 ```  
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;  
 ```  
  
5.  アプリケーションの `InitInstance` メソッドが、その親の `InitInstance` メソッド ( [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) または `CWinAppEx::InitInstance`に追加された機能です。 `InitInstance` メソッドには、 `m_dwRestartManagerSupportFlags` パラメーターをチェックする責任があります。  
  
6.  アプリケーションをコンパイルして実行します。  
  
## <a name="see-also"></a>関連項目  
 [CDataRecoveryHandler クラス](../mfc/reference/cdatarecoveryhandler-class.md)   
 [CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)   
 [CWinApp クラス](../mfc/reference/cwinapp-class.md)   
 [CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)   
 [CDocument::OnDocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)

