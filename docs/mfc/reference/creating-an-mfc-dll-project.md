---
title: "MFC DLL プロジェクトの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcdll.project
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [C++], creating projects
- DLLs [C++], MFC
- projects [C++], creating
- DLLs [C++], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: c403d1351c43e043fd3048d342dafcf069951446
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="creating-an-mfc-dll-project"></a>MFC DLL プロジェクトの作成
MFC DLL とは、複数のアプリケーションで同時に利用できる関数の共有ライブラリとして機能する、バイナリ ファイルです。 MFC DLL プロジェクトを作成する最も簡単な方法は、MFC DLL ウィザードを使用する方法です。  
  
> [!NOTE]
>  IDE に表示される機能は、有効にされている設定やエディションに依存し、ヘルプに記載されている内容とは異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>MFC DLL ウィザードを使用して MFC DLL プロジェクトを作成するには  
  
1.  ヘルプ トピックの指示に従って、 [Visual C のアプリケーション ウィザードでプロジェクトを作成する](../../ide/creating-desktop-projects-by-using-application-wizards.md)です。  
  
 **注**で、**新しいプロジェクト**ダイアログ ボックスで、`MFC DLL`を開くには、MFC DLL ウィザードの [テンプレート] ペインでアイコン。  
  
1.  使用して、アプリケーション設定を定義、[アプリケーション設定](../../mfc/reference/application-settings-mfc-dll-wizard.md)のページ、 [MFC DLL ウィザード](../../mfc/reference/mfc-dll-wizard.md)します。  
  
    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。  
  
2.  をクリックして**完了**で新しいプロジェクト ウィザードを閉じてから開きに**ソリューション エクスプ ローラー**します。  
  
 作成したプロジェクトのファイルは、ソリューション エクスプローラーで確認できます。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類の詳細については、次を参照してください。 [Visual c プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)します。  
  
## <a name="see-also"></a>関連項目  
 [Visual C プロジェクトの種類](http://msdn.microsoft.com/library/912b4ba2-7719-43d5-b087-db33e3f9329a)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [プロパティ ページ](../../ide/property-pages-visual-cpp.md)   
 [アプリケーションを展開します。](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)


