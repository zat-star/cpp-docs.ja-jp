---
title: "アプリケーションの設定、ATL プロジェクト ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.atl.com.appset
dev_langs:
- C++
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8514cce9dc2732d4a97ac51895e1ab28975fcfa3
ms.lasthandoff: 02/24/2017

---
# <a name="application-settings-atl-project-wizard"></a>[アプリケーションの設定] (ATL プロジェクト ウィザード)
使用して、**アプリケーション設定**ATL プロジェクト ウィザードのページを設計および新しい ATL プロジェクトに基本的な機能を追加します。  
  
## <a name="server-type"></a>サーバーの種類  
 次の&3; つのサーバーの種類のいずれかから選択します。  
  
 **ダイナミック リンク ライブラリ (DLL)**  
 選択すると、インプロセス サーバーを作成します。  
  
 **実行可能 (EXE)**  
 選択すると、ローカルのアウト プロセス サーバーを作成します。 このオプションは、MFC または COM + 1.0 のサポートを許可しません。 プロキシ/スタブ コードのマージのことはできません。  
  
 **サービス (EXE)**  
 Windows の起動時に、バック グラウンドで実行される Windows アプリケーションの作成を選択します。 このオプションは、MFC または COM + 1.0 のサポートを許可しないか、プロキシやスタブ コードのマージを許可しておらずします。  
  
## <a name="additional-options"></a>[追加オプション]  
  
> [!NOTE]
>  その他のオプションは、DLL プロジェクトのみで使用可能です。  
  
 **プロキシ/スタブ コードのマージを許可します。**  
 選択、**プロキシ/スタブ コードのマージを許可する**チェック ボックスをオンしやすくするためのインターフェイスをマーシャ リングすることが必要な場合です。 このオプションによって、MIDL で生成されたプロキシとスタブ コードを同じサーバーとして実行可能ファイルです。  
  
 **MFC のサポート**  
 オブジェクトが、MFC サポートが含まれることを選択します。 クラスと含まれている関数のいずれかがアクセスできるように、このオプションは、プロジェクトを MFC ライブラリにリンクします。  
  
 **COM + 1.0 のサポート**  
 COM + 1.0 コンポーネントをサポートするためにプロジェクトのビルド設定の変更を選択します。 ライブラリの標準の一覧だけでなく、ウィザードには COM + 1.0 コンポーネント固有のライブラリ comsvcs.lib が追加されます。  
  
 さらに、mtxex.dll は、アプリケーションを起動する場合、ホスト システムに読み込まれた遅延です。  
  
-   **コンポーネントの登録をサポートして**ATL プロジェクトに COM + 1.0 コンポーネントに対するサポートが含まれている場合は、このオプションを設定することができます。 コンポーネントのレジスタは、コンポーネントの一覧の取得、コンポーネントを登録または (個別にまたはを一度に) コンポーネントの登録を解除するには、COM + 1.0 オブジェクトを使用します。  
  
## <a name="see-also"></a>関連項目  
 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)


