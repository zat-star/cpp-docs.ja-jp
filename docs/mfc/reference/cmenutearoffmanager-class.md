---
title: "CMenuTearOffManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenuTearOffManager
dev_langs:
- C++
helpviewer_keywords:
- CMenuTearOffManager class
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: 31
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 53677bbea54e428e5f080f5c1f73c576abcf99a5
ms.lasthandoff: 02/24/2017

---
# <a name="cmenutearoffmanager-class"></a>CMenuTearOffManager クラス
ティアオフ メニューを管理します。 ティアオフ メニューはメニュー バー上のメニューの一種です。 ユーザーは、ティアオフ メニューをメニュー バーから外して、フローティング メニューにすることができます。  
  
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
|[CMenuTearOffManager::Initialize](#initialize)|初期化、`CMenuTearOffManager`オブジェクトです。|  
|[CMenuTearOffManager::IsDynamicID](#isdynamicid)||  
|[CMenuTearOffManager::Parse](#parse)||  
|[CMenuTearOffManager::Reset](#reset)||  
|[CMenuTearOffManager::SetInUse](#setinuse)||  
|[CMenuTearOffManager::SetupTearOffMenus](#setuptearoffmenus)||  
  
## <a name="remarks"></a>コメント  
 アプリケーションでティアオフ メニューを使用するのには必要な`CMenuTearOffManager`オブジェクトです。 ほとんどの場合に、作成または初期化するされません、`CMenuTearOffManager`オブジェクトに直接します。 これは、処理は、呼び出すときに、 [CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)関数です。  
  
## <a name="example"></a>例  
 次の例では、構築して初期化する方法、`CMenuTearOffManager`オブジェクトを呼び出して、`CWinAppEX::EnableTearOffMenus`メソッドです。 このコード スニペットの一部である、 [Word パッド サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_WordPad&#12;](../../mfc/reference/codesnippet/cpp/cmenutearoffmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenuTearOffManager`   
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmenutearoffmanager.h  
  
##  <a name="a-namebuilda--cmenutearoffmanagerbuild"></a><a name="build"></a>CMenuTearOffManager::Build  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Build(
    UINT uiTearOffBarID,  
    CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiTearOffBarID`  
 [入力] `strText`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecmenutearoffmanagera--cmenutearoffmanagercmenutearoffmanager"></a><a name="cmenutearoffmanager"></a>CMenuTearOffManager::CMenuTearOffManager  
 構築、 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)オブジェクトです。  
  
```  
CMenuTearOffManager();
```  
  
### <a name="remarks"></a>コメント  
 ほとんどの場合は作成しないで、`CMenuTearOffManager`手動でします。 アプリケーションのフレームワークを作成、`CMenuTearOffManager`オブジェクトを呼び出すと[CWinAppEx::EnableTearOffMenus](../../mfc/reference/cwinappex-class.md#enabletearoffmenus)します。  
  
##  <a name="a-namegetregpatha--cmenutearoffmanagergetregpath"></a><a name="getregpath"></a>CMenuTearOffManager::GetRegPath  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
LPCTSTR GetRegPath() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameinitializea--cmenutearoffmanagerinitialize"></a><a name="initialize"></a>CMenuTearOffManager::Initialize  
 初期化、 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)オブジェクトです。  
  
```  
BOOL Initialize(
    LPCTSTR lpszRegEntry,  
    UINT uiTearOffMenuFirst,  
    UINT uiTearOffMenuLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszRegEntry`  
 レジストリ エントリのパスを含む文字列です。 アプリケーションでは、このレジストリ エントリでティアオフ バーの設定が格納されます。  
  
 [入力] `uiTearOffMenuFirst`  
 ティアオフ メニューの最初のメニューの ID。  
  
 [入力] `uiTearOffMenuLast`  
 ティアオフ メニューの最後のメニューの ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニュー Id の範囲`uiTearOffMenuFirst`に`uiTearOffMenuLast`に連続した間隔にする必要があります。 間隔は、アプリケーションで同時に表示される可能性がティアオフ メニューの数を定義します。  
  
##  <a name="a-nameisdynamicida--cmenutearoffmanagerisdynamicid"></a><a name="isdynamicid"></a>CMenuTearOffManager::IsDynamicID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsDynamicID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameparsea--cmenutearoffmanagerparse"></a><a name="parse"></a>CMenuTearOffManager::Parse  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
UINT Parse(CString& str);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `str`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namereseta--cmenutearoffmanagerreset"></a><a name="reset"></a>CMenuTearOffManager::Reset  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void Reset(HMENU hmenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hmenu`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetinusea--cmenutearoffmanagersetinuse"></a><a name="setinuse"></a>CMenuTearOffManager::SetInUse  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetInUse(
    UINT uiCmdId,  
    BOOL bUse = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdId`  
 [入力] `bUse`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetuptearoffmenusa--cmenutearoffmanagersetuptearoffmenus"></a><a name="setuptearoffmenus"></a>CMenuTearOffManager::SetupTearOffMenus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetupTearOffMenus(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hMenu`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)

