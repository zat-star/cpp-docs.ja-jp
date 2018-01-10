---
title: "CMenuTearOffManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::CMenuTearOffManager
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Build
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::GetRegPath
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Initialize
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::IsDynamicID
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Parse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::Reset
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetInUse
- AFXMENUTEAROFFMANAGER/CMenuTearOffManager::SetupTearOffMenus
dev_langs: C++
helpviewer_keywords:
- CMenuTearOffManager [MFC], CMenuTearOffManager
- CMenuTearOffManager [MFC], Build
- CMenuTearOffManager [MFC], GetRegPath
- CMenuTearOffManager [MFC], Initialize
- CMenuTearOffManager [MFC], IsDynamicID
- CMenuTearOffManager [MFC], Parse
- CMenuTearOffManager [MFC], Reset
- CMenuTearOffManager [MFC], SetInUse
- CMenuTearOffManager [MFC], SetupTearOffMenus
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efb1b7acc2f4eb779de49559b5b566e89d518a0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager クラス
ティアオフ メニューを管理します。 ティアオフ メニューはメニュー バー上のメニューの一種です。 ユーザーは、ティアオフ メニューをメニュー バーから外して、フローティング メニューにすることができます。  
  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>構文  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMenuTearOffManager::CMenuTearOffManager](#cmenutearoffmanager)|`CMenuTearOffManager` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMenuTearOffManager::Build](#build)||  
|[CMenuTearOffManager::GetRegPath](#getregpath)||  
|[CMenuTearOffManager::Initialize](#initialize)|初期化、`CMenuTearOffManager`オブジェクト。|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>コメント  
 ティアオフ メニューをアプリケーションで使用するためにする必要があります、`CMenuTearOffManager`オブジェクト。 ほとんどの場合に、作成または初期化するされません、`CMenuTearOffManager`オブジェクトに直接できます。 これは自動的に処理を呼び出すとき、 [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)関数。  
  
## <a name="example"></a>例  
 次の例では、構築および初期化する方法、`CMenuTearOffManager`オブジェクトを呼び出して、`CWinAppEX::EnableTearOffMenus`メソッド。 このコード スニペットは、 [Word パッド サンプル](../../visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxmenutearoffmanager.h  
  
##  <a name="build"></a>CMenuTearOffManager::Build  

  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiTearOffBarID`  
 [入力] `strText`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cmenutearoffmanager"></a>CMenuTearOffManager::CMenuTearOffManager  
 構築、 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)オブジェクト。  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>コメント  
 ほとんどの場合、作成しないようにする、`CMenuTearOffManager`手動でします。 アプリケーションのフレームワークを作成、`CMenuTearOffManager`オブジェクトを呼び出すとき[CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)です。  
  
##  <a name="getregpath"></a>CMenuTearOffManager::GetRegPath  

  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="initialize"></a>CMenuTearOffManager::Initialize  
 初期化、 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)オブジェクト。  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszRegEntry`  
 レジストリ エントリのパスを含む文字列。 アプリケーションは、このレジストリ エントリでティアオフ バーの設定を格納します。  
  
 [入力] `uiTearOffMenuFirst`  
 ティアオフ メニューの最初のメニューの ID。  
  
 [入力] `uiTearOffMenuLast`  
 ティアオフ メニューの最後のメニューの ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニュー Id の範囲`uiTearOffMenuFirst`に`uiTearOffMenuLast`継続的な間隔である必要があります。 間隔は、アプリケーションで同時に表示される可能性がティアオフ メニューの数を定義します。  
  
##  <a name="isdynamicid"></a>CMenuTearOffManager::IsDynamicID  

  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="parse"></a>CMenuTearOffManager::Parse  

  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `str`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="reset"></a>CMenuTearOffManager::Reset  

  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hmenu`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setinuse"></a>CMenuTearOffManager::SetInUse  

  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdId`  
 [入力] `bUse`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setuptearoffmenus"></a>CMenuTearOffManager::SetupTearOffMenus  

  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenu`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)
