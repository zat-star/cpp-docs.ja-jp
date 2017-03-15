---
title: "CMultiDocTemplate クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- MDI, template
- CMultiDocTemplate class
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 6e58325cd4dcaec01bf8a76006bb397fccd9a171
ms.lasthandoff: 02/24/2017

---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate クラス
MDI (マルチ ドキュメント インターフェイス) を実装するドキュメント テンプレートを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMultiDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|`CMultiDocTemplate` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 MDI アプリケーションでは、ドキュメントを表示する各ユーザーが&0; 個以上のドキュメント フレーム ウィンドウを開くことができますワークスペースとしてメイン フレーム ウィンドウを使用します。 MDI のより詳細な説明を参照してください。*ソフトウェア設計のための Windows インターフェイスのガイドライン*します。  
  
 ドキュメント テンプレートには、3 種類のクラス間の関係を定義します。  
  
-   派生するドキュメント クラス[CDocument](../../mfc/reference/cdocument-class.md)します。  
  
-   ビュー クラス上に示したドキュメント クラスからのデータが表示されます。 このクラスから派生できます[CView](../../mfc/reference/cview-class.md)、 `CScrollView`、 `CFormView`、または`CEditView`です。 (使用することも`CEditView`直接)。  
  
-   ビューを含むフレーム ウィンドウ クラスです。 MDI のドキュメント テンプレートからこのクラスを派生できます`CMDIChildWnd`、あるいはを使用中のドキュメント フレーム ウィンドウの動作をカスタマイズする必要はありません、 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)独自のクラスを派生させることがなく直接します。  
  
 MDI アプリケーションは、ドキュメントの&1; つ以上の種類をサポートできますが、異なる種類のドキュメントを同時に開くことができます。 アプリケーションでは、サポートされているドキュメントの種類ごとに&1; つのドキュメント テンプレートを持ちます。 たとえば、MDI アプリケーションでは、スプレッドシートやテキスト ドキュメントの両方をサポートする場合、アプリケーションが&2; つ`CMultiDocTemplate`オブジェクトです。  
  
 アプリケーションは、ユーザーが新しいドキュメントを作成するときに、ドキュメント テンプレートを使用します。 アプリケーションでは、ドキュメントの&1; つ以上の種類をサポートするフレームワークはドキュメント テンプレートからサポートされているドキュメントの種類の名前を取得し、新しいファイル ダイアログ ボックスの一覧に表示されます。 ユーザーがドキュメントの種類を選択すると、アプリケーションはドキュメント クラスのオブジェクト、フレーム ウィンドウのオブジェクト、およびビューのオブジェクトを作成し、それらを相互に接続します。  
  
 すべてのメンバーの関数を呼び出す必要はありません`CMultiDocTemplate`を除き、コンス トラクターです。 Framework ハンドル`CMultiDocTemplate`オブジェクトを内部的にします。  
  
 詳細については`CMultiDocTemplate`を参照してください[ドキュメント テンプレートとドキュメント/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecmultidoctemplatea--cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a>CMultiDocTemplate::CMultiDocTemplate  
 `CMultiDocTemplate` オブジェクトを構築します。  
  
```  
CMultiDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDResource`  
 ドキュメントの種類に使用されているリソースの ID を指定します。 これには、メニューのアイコン、アクセラレータ テーブル、および文字列リソースが含まれます。  
  
 文字列リソースは、"\n"文字で区切られた最大&7; つの部分文字列で構成されます (部分文字列が含まれていない場合は、プレース ホルダーとして"\n"文字が必要。 ただし、末尾の"\n"文字は必要ありません) です。これらの部分文字列では、ドキュメントの種類について説明します。 詳細については、部分文字列は、次を参照してください。 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)します。 アプリケーションのリソース ファイルでは、この文字列リソースが見つかります。 例:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 文字列の先頭が"\n"文字であることに注意してください。これは、最初の部分文字列が MDI アプリケーションで実行されていない、したがってが含まれていないためです。 ストリング エディターを使用してこの文字列を編集することができます。文字列全体は、7 つの別のエントリとしてではなく文字列エディターで、1 つのエントリとして表示されます。  
  
 これらのリソースの種類の詳細については、次を参照してください。[リソース エディター](../../windows/resource-editors.md)します。  
  
 `pDocClass`  
 指す、`CRuntimeClass`ドキュメント クラスのオブジェクト。 このクラスは、 **CDocument**-には、ドキュメントを表すために定義するクラスを派生します。  
  
 `pFrameClass`  
 指す、`CRuntimeClass`フレーム ウィンドウ クラスのオブジェクト。 このクラスを指定できます、 `CMDIChildWnd`-派生クラス、またはできます`CMDIChildWnd`自体、ドキュメント フレーム ウィンドウの既定の動作をする場合。  
  
 `pViewClass`  
 指す、`CRuntimeClass`ビュー クラスのオブジェクト。 このクラスは、 `CView`-には、ドキュメントを表示するように定義するクラスを派生します。  
  
### <a name="remarks"></a>コメント  
 いずれかを動的に割り当てる`CMultiDocTemplate`各ドキュメントの種類をアプリケーションがサポートし、それぞれを渡すオブジェクト`CWinApp::AddDocTemplate`から、`InitInstance`アプリケーション クラスのメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&92;](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 2 番目の例を次に示します。  
  
 [!code-cpp[NVC_MFCDocView #&93;](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [関数のクラス](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)

