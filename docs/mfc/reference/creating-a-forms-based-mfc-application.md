---
title: "フォーム ベースの MFC アプリケーションを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcforms.project
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
caps.latest.revision: 12
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
ms.openlocfilehash: b95d52f5ecf97f43bd21dd0f2a8c4fd478431ce3
ms.lasthandoff: 02/24/2017

---
# <a name="creating-a-forms-based-mfc-application"></a>フォーム ベースの MFC アプリケーションの作成
フォームとは、ユーザーがデータのアクセスや変更に使用できる、コントロール付きのダイアログ ボックスです。 フォームをユーザーが選択できるアプリケーションを開発することもできます。 一般的には、フォーム ベースのアプリケーションにより、ユーザーのアクセス フォームのクリックによって**新規**から、**ファイル**メニュー。 ユーザーへのアクセスを許可しないはダイアログ ベースのアプリケーション、**新規**オプション、**ファイル**] メニューの [はフォーム ベースのアプリケーションもと見なされます。  
  
 シングル ドキュメント インターフェイス (SDI: Single Document Interface) のフォーム ベースのアプリケーションでは、一度に実行できるフォームのインスタンスは&1; つだけです。 新しいフォームを選択して、SDI フォーム ベースのアプリケーションから同時にさまざまなフォームを実行することは、**新規**オプション、**ファイル**メニュー。  
  
 マルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) のフォーム ベースのアプリケーションを作成すると、同一フォームの複数のインスタンスをアプリケーションでサポートできます。  
  
 マルチ トップレベル ドキュメントをサポートするアプリケーションを作成すると、デスクトップがそのドキュメントの暗黙の親となり、ドキュメントのフレームがアプリケーションのクライアント領域に限定されることはありません。 ドキュメントの複数のインスタンスを開くことができます。各インスタンスにはフレーム、メニュー、タスク バー アイコンが含まれます。 選択した場合は、ドキュメントのそれ以降のインスタンスを個別に閉じることができます、`Exit`オプションを**ファイル**初期のインスタンスでは、アプリケーションのメニューは、すべてのインスタンスを終了します。  
  
 SDI、MDI、およびマルチ トップレベル ドキュメント アプリケーションはすべてフォーム ベースであり、ドキュメント/ビュー アーキテクチャを使用します。  
  
 定義上は、ダイアログ ベースのアプリケーションもすべてフォーム ベースになります。 ダイアログ ベースのアプリケーションでは、ドキュメント/ビュー アーキテクチャが使用されないため、独自の追加フォームの作成およびそのアクセス方法は自分で管理する必要があります。  
  
 フォーム ベースのアプリケーションの基本クラスは[CFormView](../../mfc/reference/cformview-class.md)します。 アプリケーションでデータベースをサポートする場合は、`CFormView` の任意の派生クラスも選択できます。 フォームとは、`CFormView` から派生するウィンドウ、または `CFormView` から継承されたクラスから派生するウィンドウです。  
  
 基本クラスを使用する場合でも[CView](../../mfc/reference/cview-class.md)、行うことができます後で、アプリケーションでフォームに基づく[MFC クラスの追加](../../mfc/reference/adding-an-mfc-class.md)から派生した`CFormView`とチェック、**ドキュメント テンプレートの生成**のチェック ボックスを[MFC クラス ウィザード](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md)します。  
  
 ウィザードを終了するとプロジェクトが開きます。基底クラスとして `CFormView` (または `CFormView` から継承されたクラス) を選択した場合、あるいはダイアログ ベースのアプリケーションを作成した場合は、Visual C++ によってダイアログ エディターが開かれます。 これで最初のフォームをデザインする準備が整いました。  
  
### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>フォーム ベースの MFC アプリケーションの作成を開始するには  
  
1.  手順に従い[MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)します。  
  
2.  MFC アプリケーション ウィザードで[アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md)] ページで、[、**ドキュメント/ビュー アーキテクチャ サポート**チェック ボックスをオンします。  
  
3.  選択**1 つのドキュメント**、**複数のドキュメント**、または**複数のトップレベル ドキュメント**します。  
  
    > [!NOTE]
    >  既定では、SDI、MDI、または複数のトップレベル ドキュメント インターフェイス アプリケーションを選択した場合`CView`でのアプリケーションのビューの基底クラスとして設定されている、[生成されたクラス](../../mfc/reference/generated-classes-mfc-application-wizard.md)ウィザードのページです。 フォーム ベースのアプリケーションを作成するには、アプリケーションのビューの基底クラスとして `CFormView` を選択する必要があります。 ウィザードは、フォーム ベースのアプリケーションの印刷はサポートしていません。  
  
4.  ウィザードのその他のページで、必要なプロジェクト オプションを設定します。  
  
5.  をクリックして**完了**スケルトン アプリケーションを生成します。  
  
 詳細については次を参照してください:  
  
-   [派生ビュー クラス](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [ドキュメント/ビュー アーキテクチャの代替手段](../../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [アプリケーションの設計のオプション](../../mfc/application-design-choices.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)   
 [フォーム ビュー](../../mfc/form-views-mfc.md)   
 [ファイル エクスプ ローラー スタイルの MFC アプリケーションの作成](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)   
 [Web ブラウザー形式の MFC アプリケーションの作成](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)


