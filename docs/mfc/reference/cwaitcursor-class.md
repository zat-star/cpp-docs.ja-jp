---
title: "CWaitCursor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs:
- C++
helpviewer_keywords:
- cursors, wait cursor
- CWaitCursor class
- wait cursors
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
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
ms.openlocfilehash: f72598c356add5d891b013f1fd7b87665c5a6c63
ms.lasthandoff: 02/24/2017

---
# <a name="cwaitcursor-class"></a>CWaitCursor クラス
時間がかかる処理を実行している最中に、通常は砂時計として表示される待機カーソルを表示する&1; つの方法を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CWaitCursor  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](#cwaitcursor)|構築、`CWaitCursor`オブジェクトし、待機カーソルを表示します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWaitCursor::Restore](#restore)|変更された後に待機カーソルを復元します。|  
  
## <a name="remarks"></a>コメント  
 `CWaitCursor`基本クラスはありません。  
  
 正確な Windows プログラミングでは、かなりの時間を取得する操作を実行するときに待機カーソルを表示することが必要です。  
  
 待機カーソルを表示する単を定義する、`CWaitCursor`時間のかかる操作を実行するコードの前に変数です。 オブジェクトのコンス トラクターは、自動的に表示される待機カーソルをさせます。  
  
 オブジェクトがスコープから外れる場合 (するブロックの最後に、`CWaitCursor`オブジェクトが宣言されている)、デストラクターを以前のカーソル、カーソルを設定します。 つまり、オブジェクトを自動的に必要なクリーンアップを実行します。  
  
> [!NOTE]
>  コンス トラクターとデストラクターの動作のため`CWaitCursor`オブジェクトは常にローカル変数として宣言、グローバル変数として宣言もで割り当てられた、**新しい**します。  
  
 カーソルが、メッセージ ボックスまたはダイアログ ボックスで、呼び出しが表示されるように、変更する操作を実行する場合、[復元](#restore)に待機カーソルを戻します。 呼び出すことが**復元**待機カーソルが表示されているときにもします。  
  
 待機カーソルを表示する別の方法は、の組み合わせを使用する[CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)、 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)、そして[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)します。 ただし、`CWaitCursor`時間のかかる操作を完了したら、以前のカーソルにカーソルを設定する必要があるために使用する方が簡単です。  
  
> [!NOTE]
>  MFC を設定し、カーソルを使用して、復元、 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)仮想関数。 カスタム動作を提供するには、この関数をオーバーライドすることができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CWaitCursor`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&62;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="cwaitcursor"></a>CWaitCursor::CWaitCursor  
 待機カーソルを表示するだけ宣言、`CWaitCursor`時間のかかる操作を実行するコードの前にオブジェクトです。  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、自動的に表示される待機カーソルをさせます。  
  
 オブジェクトがスコープから外れる場合 (するブロックの最後に、`CWaitCursor`オブジェクトが宣言されている)、デストラクターを以前のカーソル、カーソルを設定します。 つまり、オブジェクトを自動的に必要なクリーンアップを実行します。  
  
 事実、関数の一部のみに待機カーソルをアクティブにする (可能性のある関数の終了前に)、ブロックの最後に、デストラクターが呼び出されることを利用できます。 この手法は、次の&2; つ目の例に示します。  
  
> [!NOTE]
>  コンス トラクターとデストラクターの動作のため`CWaitCursor`オブジェクトは常にローカル変数として宣言、グローバル変数として宣言もで割り当てられた、**新しい**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&63;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="restore"></a>CWaitCursor::Restore  
 待機カーソルを復元するには、メッセージ ボックスや待機カーソルを別のカーソルに変わることがあります ダイアログ ボックスを表示するなどの操作を実行する後にこの関数を呼び出します。  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>コメント  
 [Ok] を呼び出すことが**復元**待機カーソルが表示されているときにもします。  
  
 いずれかではない関数内で待機カーソルを復元する必要がある場合、`CWaitCursor`オブジェクトが宣言されている、呼び出すことができます[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&64;](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [どのように i: Microsoft Foundation クラスのアプリケーションにマウス ポインターを変更します。](http://go.microsoft.com/fwlink/linkid=128044)




