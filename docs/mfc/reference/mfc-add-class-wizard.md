---
title: "MFC クラス追加ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
caps.latest.revision: 16
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 08d258c2b8386a4dd0c1d24c6ac6aa10f6c04a63
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-add-class-wizard"></a>MFC クラス追加ウィザード
このコード ウィザードを使用して、既存の MFC プロジェクトにクラスを追加または MFC をサポートする ATL プロジェクトにクラスを追加します。 MFC がサポートしている Win32 プロジェクトに MFC クラスを追加することもできます。 プロジェクトの作成時に指定した機能は、このダイアログ ボックスで使用可能なオプションを決定します。  
  
## <a name="names"></a>名前  
 このページで、クラス名、基本クラスと新しいクラスのファイル名を指定します。  
  
 **クラス名**  
 新しいクラスの名前を指定し、Id とこのページ上のファイルの名前の既定の基盤を提供します。 C++ クラス、たとえば、""が「が付きます」、通常"C"で開始します。  
  
 **基本クラス**  
 新しいクラスの基本クラスの名前を指定します。 基本クラスは、既定では、 [CWnd](../../mfc/reference/cwnd-class.md)します。 選択した基本クラスでは、このページの他のボックスがアクティブかどうかを決定します。  
  
 基本クラスでは、ダイアログの ID またはリソース ID に、クラスがあるかどうかを判断すると、設定するクラスの型 クラスの一般的な種類は次のとおりです。  
  
-   などのクラス[CButton](../../mfc/reference/cbutton-class.md)、 [CWnd](../../mfc/reference/cwnd-class.md)、または[CDocument](../../mfc/reference/cdocument-class.md)、ダイアログ ボックスが不要 ID またはリソース id。 これらのクラスは、ダイアログ ボックスまたはリソース ID を使用しないでください。 基本クラスのこれらのクラスのいずれかを選択した場合、**ダイアログ ID**ボックスおよび**DHTML リソース ID**ボックスは淡色表示になります。  
  
-   などのクラス[CDialog](../../mfc/reference/cdialog-class.md)、 [CFormView](../../mfc/reference/cformview-class.md)、または[CPropertyPage](../../mfc/reference/cpropertypage-class.md)ダイアログの ID が必要な  
  
-   クラス[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)ダイアログの ID、DHTML リソース ID、および HTML ファイル名必要があります。  
  
 クラスについては、ダイアログの ID を必要とする、した方がより効果的に使用、[リソース エディター](../../windows/resource-editors.md)ダイアログ リソースを作成するには、その ID を割り当てる、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、し、そのリソース ID に関連付けられているクラスを作成 参照してください[ ダイアログ ボックスの新規作成](../../windows/creating-a-new-dialog-box.md)標準の Windows ダイアログ ボックスを作成する方法についてです。  
  
> [!NOTE]
>  最初ダイアログ リソースを作成してから新しいクラスを派生させるかどうか`CDHtmlDialog`、標準の Windows を削除**OK**と**キャンセル**既定 ダイアログ ボックスに表示されるボタン。 Windows の標準のダイアログ ボックスがそれ自体を含む DHTML フォームをホスト**OK**と**キャンセル**ボタン。  
  
 ダイアログ ボックスには、Windows のコントロールと DHTML コントロールの両方を含めることができますは推奨されません。  
  
 **ダイアログの ID**  
 選択した場合に、ダイアログ ボックスの ID を指定する`CDialog`、 `CFormView`、 `CPropertyPage`、または`CDHtmlDialog`として、**基本クラス**します。  
  
 **.h ファイル**  
 新しいオブジェクトのクラスのヘッダー ファイルの名前を設定します。 既定では、この名前はで指定した名前に基づく**クラス名**します。 ファイル名を任意の場所に保存するか、既存のファイルに、クラス宣言を追加する、省略記号ボタンをクリックします。 既存のファイルを選択すると場合、ウィザードは保存されません選択した場所に表示されるまで をクリック**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードでは、クラス宣言がファイルの内容に追加されるかどうかを指定するように求められます。 をクリックして**はい**ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
 **.cpp ファイル**  
 新しいオブジェクトのクラスの実装ファイルの名前を設定します。 既定では、この名前はで指定した名前に基づく**クラス名**します。 任意の場所にファイル名を保存する、省略記号ボタンをクリックします。 クリックするまで、選択した場所にファイルが保存されません**完了**ウィザード。  
  
 ウィザードでは、ファイルは上書きされません。 クリックすると、既存のファイルの名前を選択するかどうかは**完了**ウィザードでは、クラスの実装が、ファイルの内容に追加されるかどうかを指定するように求められます。 をクリックして**はい**ファイルを追加する をクリックして**なし**ウィザードに戻り、別のファイル名を指定します。  
  
 **アクティブなユーザー補助機能**  
 呼び出して Active Accessibility 用の MFC のサポートを有効に[EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility)コンス トラクターでします。 このオプションから派生したクラスの使用可能な[CWnd](../../mfc/reference/cwnd-class.md)します。  
  
 **DHTML リソース ID**  
 派生したクラスに適用されます`CDHtmlDialog`のみです。 DHTML ダイアログ ボックスのリソース ID を指定します。 リソース ID は、HTML ダイアログ ボックスのファイル名と共に、プロジェクトの .rc ファイルの HTML セクションに表示されます。 識別されるダイアログ ボックスによってホストされる DHTML リソースは、この ID で識別される**ダイアログ ID**します。  
  
 **.HTM ファイル**  
 派生したクラスに適用されます`CDHtmlDialog`のみです。 DHTML のダイアログ ボックスの HTML ファイルの名前を設定します。 既定では、このファイル名は、クラス名に基づいています。 HTML」DHTML ダイアログ ボックスのリソース ID と共に、プロジェクトの .rc ファイルのファイル名が表示されます。  
  
 **オートメーション**  
 サポートのクラス レベルを設定[オートメーション](../../mfc/automation.md)します。 クラス レベルでのオートメーションは、オートメーションをサポートするすべてのクラスに対して有効です。 オートメーションのサポートで作成したプロジェクトの利用もできます。 いずれか、MFC をプロジェクトには、 [ATL サポート](../../atl/reference/mfc-support-in-atl-projects.md)、または選択した MFC プロジェクト、**オートメーション**チェック ボックスをオンに、[高度な機能](../../mfc/reference/advanced-features-mfc-application-wizard.md)MFC アプリケーション ウィザードのページです。  
  
|オプション|説明|  
|------------|-----------------|  
|**None**|クラスにオートメーションによるサポートがないことを示します。|  
|**オートメーション**|クラスがオートメーションをサポートしていることを示します。 このオプションを選択する場合、新しく作成されたクラスは Microsoft Visual Basic や Microsoft Excel などのオートメーション クライアント アプリケーションでのプログラミング可能なオブジェクトとして使用可能です。 このオプションでは、この表の後に記載されている基本クラスを使用できません。|  
|**型 ID を使用して作成可能**|クラスとプロジェクトの両方がオートメーションを使用してこのクラスのオブジェクトを作成するその他のアプリケーションをサポートすることを示します。 このオプションを使用して、オートメーション クライアントはオートメーション オブジェクトを直接作成できます。 クライアント アプリケーションで作成されるオブジェクトを指定するテキスト ボックス内の型 ID が使用されます。システム全体と、一意である必要があります。 このオプションでは、この表の後に記載されている基本クラスを使用できません。|  
  
 オートメーションのサポートでは、次の基本クラスを使用できません。  
  
-   `CAsyncMonitorFile`  
  
-   `CAsyncSocket`  
  
-   `CCachedDataPathProperty`  
  
-   `CConnectionPoint`  
  
-   `CDatabase`  
  
-   `CDataPathProperty`  
  
-   `CHttpFilter`  
  
-   `CHttpServer`  
  
-   `CInternetSession`  
  
-   `CObject`  
  
-   `CSocket`  
  
 **種類 ID**  
 クラスの型 ID を設定します。 **タイプ ID**  ボックスには、次のようにするプロジェクトの名前と新しいクラスの名前が連結: *MFCProj.MFCClass*します。 この ID を変更できるは、選択した場合にのみ、**オートメーション**オプション**型の ID で作成可能**します。  
  
 **ドキュメント テンプレート リソースを生成します。**  
 アプリケーションによって作成されたドキュメントのドキュメント テンプレート リソースことを示します。 このチェック ボックスをアクティブ化する、プロジェクトが MFC ドキュメント/ビュー アーキテクチャをサポートし、このクラスの基本クラスである必要があります[CFormView](../../mfc/reference/cformview-class.md)します。  
  
 参照してください[ドキュメント テンプレートとドキュメント/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)の詳細。  
  
## <a name="see-also"></a>関連項目  
 [MFC クラス](../../mfc/reference/adding-an-mfc-class.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)

