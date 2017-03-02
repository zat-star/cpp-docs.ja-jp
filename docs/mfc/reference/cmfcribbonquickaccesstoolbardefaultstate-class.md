---
title: "CMFCRibbonQuickAccessToolBarDefaultState クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState class
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
caps.latest.revision: 28
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
ms.openlocfilehash: 211e8d897de923e7f07df389b0e9e7218cf45872
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState クラス
リボン バーに配置されるクイック アクセス ツールバーの既定の状態を管理するヘルパー クラス ( [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md))。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|`CMFCRibbonQuickAccessToolbarDefaultState` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|既定の状態に、クイック アクセス ツールバーのコマンドを追加します。 これは、操作ではツールバー自体は変更されません。|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|別の&1; つのクイック アクセス ツールバーのプロパティをコピーします。|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|クイック アクセス ツールバーからすべてのコマンドを削除します。 これは、操作ではツールバー自体は変更されません。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションで、クイック アクセス ツールバーを作成した後を呼び出すことによって、既定の状態を設定することお勧め[CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)します。 ユーザーがクリックしたときに、この既定の状態を復元、**リセット**のボタンでは、**カスタマイズ**、アプリケーションのページ**オプション** ダイアログ ボックス。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCRibbonQuickAccessToolbarDefaultState`クラスと既定の状態に、クイック アクセス ツールバーのコマンドを追加する方法です。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&21;](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribbonquickaccesstoolbar.h  
  
##  <a name="a-nameaddcommanda--cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a>CMFCRibbonQuickAccessToolBarDefaultState::AddCommand  
 既定の状態に、クイック アクセス ツールバーのコマンドを追加します。  
  
```  
void AddCommand(
    UINT uiCmd,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] uiCmd`  
 コマンド ID を指定します  
  
 `[in] bIsVisible`  
 クイック アクセス ツールバーが既定の状態の場合は、コマンドの表示/非表示を設定します。  
  
### <a name="remarks"></a>コメント  
 コマンドを CMFCRibbonQuickAccessToolBarDefaultState に追加するには、3 つの結果が実現しています。 最初に、追加した各コマンドは、クイック アクセス ツールバーの右側にあるドロップダウン リストに表示されます。 この方法で、ユーザーが簡単に追加またはクイック アクセス ツールバーからコマンドを削除できます。 表示する記載されているコマンドのみ表示するよう既定の状態で、ユーザーがクリックすると、クイック アクセス ツールバーをリセットする&2; 番目に、**リセット**ボタンをクリックして、**カスタマイズ** ダイアログ ボックス。 3 つ目の状態が呼び出さない場合[CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)、クイック アクセス ツールバー コマンドを使用して、表示されているこの一覧から既定の表示コマンドとして初めて、ユーザーがアプリケーションを実行します。 必要なすべてのコマンドを追加した後で呼び出す[CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)そのリボン バーのクイック アクセス ツールバーの既定の状態としてこのインスタンスを設定します。  
  
##  <a name="a-namecopyfroma--cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a>CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom  
 別の&1; つのクイック アクセス ツールバーのプロパティをコピーします。  
  
```  
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 ソースへの参照`CMFCRibbonQuickAccessToolBarDefaultState`からコピー先のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、各コマンドをコピー元の`CMFCRibbonQuickAccessToolBarDefaultState`オブジェクトがこのオブジェクトを使用して、 [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)メソッドです。  
  
##  <a name="a-namecmfcribbonquickaccesstoolbardefaultstatea--cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a>CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState  
 クイック アクセス ツールバーの既定の状態オブジェクトを構築します。  
  
```  
CMFCRibbonQuickAccessToolBarDefaultState();
```  
  
### <a name="remarks"></a>コメント  
 既定では、一連のコマンドの新しいインスタンス[CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)が含まれていますが空です。  
  
##  <a name="a-nameremovealla--cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a>CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll  
 クイック アクセス ツールバーの既定のコマンドの一覧をクリアします。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 この関数がこのインスタンスからすべてのコマンドを削除する前の呼び出し[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)を追加します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)

