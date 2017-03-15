---
title: "CCreateContext 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCreateContext
dev_langs:
- C++
helpviewer_keywords:
- CCreateContext structure
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 22
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 231f2e44e085d27a2b2cbf289adf7b0521471b0e
ms.lasthandoff: 02/24/2017

---
# <a name="ccreatecontext-structure"></a>CCreateContext 構造体
フレームワークを使用して、`CCreateContext`フレーム ウィンドウとドキュメントに関連付けられているビューの作成時に構造化します。  
  
## <a name="syntax"></a>構文  
  
```  
struct CCreateContext  
```  
  
## <a name="remarks"></a>コメント  
 `CCreateContext`構造体は、基本クラスではありません。  
  
 ウィンドウを作成するときに、この構造体の値は、そのデータのビューに、ドキュメントのコンポーネントを接続するための情報を提供します。 使用する必要があるだけ`CCreateContext`作成プロセスの一部をオーバーライドする場合。  
  
 A`CCreateContext`構造体には、ドキュメント、フレーム ウィンドウ、ビュー、およびドキュメント テンプレートへのポインターが含まれます。 ポインターも含まれています、`CRuntimeClass`を作成するビューの種類を識別します。 ランタイム クラス情報と現在のドキュメントのポインターは、新しいビューを動的に作成に使用されます。 次の表を提案する方法とタイミング各`CCreateContext`メンバーを使用する場合があります。  
  
|メンバー|型|何が|  
|------------|----------|--------------------|  
|`m_pNewViewClass`|`CRuntimeClass*`|`CRuntimeClass`作成する新しいビューです。|  
|`m_pCurrentDoc`|`CDocument*`|新しいビューに関連付ける既存のドキュメントです。|  
|`m_pNewDocTemplate`|`CDocTemplate*`|新しい MDI フレーム ウィンドウの作成時に関連付けられているドキュメント テンプレートです。|  
|`m_pLastView`|`CView*`|その他のビューは、モデル化、分割ウィンドウのビューの作成またはドキュメント上の&2; つ目のビューの作成と同様に、元のビュー|  
|`m_pCurrentFrame`|`CFrameWnd*`|その他のフレーム ウィンドウは、モデル化、2 つ目のフレーム ウィンドウにドキュメントの作成と同様に、フレーム ウィンドウ。|  
  
 格納されている情報を検証、ドキュメント テンプレートは、ドキュメントとその関連コンポーネントを作成するとき、`CCreateContext`構造体。 たとえば、存在しないドキュメントのビューを作成できません必要があります。  
  
> [!NOTE]
>  すべてのポインターの`CCreateContext`は省略可能であり`NULL`指定されていないか不明な場合です。  
  
 `CCreateContext`下に表示するメンバー関数によって使用される「関連項目」 これらをオーバーライドする場合に、特定の情報をこれらの関数の説明を参照してください。  
  
 次に、いくつかの一般的なガイドラインを示します。  
  
-   ウィンドウの作成の引数として渡されるときに`CWnd::Create`、`CFrameWnd::Create`と`CFrameWnd::LoadFrame`作成のコンテキストでは、どのような新しいウィンドウへの接続を指定します。 ほとんどのウィンドウ全体の構造は省略可能、および`NULL`ポインターを渡すことができます。  
  
-   オーバーライド可能なメンバー関数の場合など、 `CFrameWnd::OnCreateClient`、`CCreateContext`引数は省略可能です。  
  
-   メンバー関数の関連するビューでの作成、入力してください、ビューを作成するには、十分な情報。 たとえば、分割ウィンドウの最初のビューに、クラスの情報を表示したり、現在のドキュメントを指定する必要があります。  
  
 一般に、フレームワークの既定値を使用する場合は無視してかまいません`CCreateContext`します。 高度な変更、Microsoft Foundation Class ライブラリのソース コードまたは VIEWEX などのサンプル プログラムをしようとすると、説明します。 必要なパラメーターを忘れると、framework アサートされしていませんが通知されます。  
  
 詳細については`CCreateContext`、MFC サンプルを参照して[VIEWEX](../../visual-cpp-samples.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)   
 [CFrameWnd::LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)   
 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)   
 [CSplitterWnd::Create](../../mfc/reference/csplitterwnd-class.md#create)   
 [CSplitterWnd::CreateView](../../mfc/reference/csplitterwnd-class.md#createview)   
 [Cwnd::create](../../mfc/reference/cwnd-class.md#create)


