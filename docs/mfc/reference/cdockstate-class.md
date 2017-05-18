---
title: "クラスの変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs:
- C++
helpviewer_keywords:
- dock state
- size
- docking control bars
- CDockState class
- states, dockable control bar
- position, control bar
- size, control bar
- docking tool windows
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fc8beb80cc35c1816fbc305ece2bfbc5df2e7cd0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdockstate-class"></a>クラスの変更
いくつかのドッキング コントロール バーの状態を&2; 次メモリ (ファイル) で読み込み、アンロード、またはクリアするシリアル化された `CObject` クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|ドッキング状態情報をクリアします。|  
|[CDockState::GetVersion](#getversion)|格納されているのバージョン番号を取得バー状態です。|  
|[CDockState::LoadState](#loadstate)|レジストリからの情報の状態を取得しますか。INI ファイルです。|  
|[後](#savestate)|状態情報をレジストリまたは INI ファイルに保存します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|格納されているへのポインターの配列では、各コントロール バーの&1; つのエントリを持つ状態情報をドッキングします。|  
  
## <a name="remarks"></a>コメント  
 ドッキング状態には、サイズと、バーとドッキングされているかどうかの位置が含まれています。 ドッキング状態が格納されているを取得するときに`CDockState`、バーを確認位置と、バーが、現在の画面設定で表示されない場合`CDockState`バーの位置が表示されるようです。 主な目的`CDockState`は、コントロール バーの数値の全体の状態を保持し、その状態を保存して、レジストリに、アプリケーションのいずれかをロードします。INI ファイルか、またはバイナリ形式の一部として、`CArchive`オブジェクトの内容。  
  
 バーには、バー、ツールバー、ステータス バー、またはダイアログ バーなどの任意のドッキング可能なコントロールを指定できます。 `CDockState`オブジェクトは読み取りし、書き込みを使用するファイルと、`CArchive`オブジェクトです。  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate)フレーム ウィンドウのすべての状態情報を取得`CControlBar`オブジェクトおよび配置に、`CDockState`オブジェクトです。 内容を記述することができますし、`CDockState`オブジェクトを使用してストレージに[Serialize](../../mfc/reference/cobject-class.md#serialize)または[後](#savestate)します。 後で、フレーム ウィンドウのコントロール バーの状態を復元する場合での状態を読み込むことができます`Serialize`または[CDockState::LoadState](#loadstate)を使用して[CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate)フレーム ウィンドウのコントロール バーに保存された状態を適用します。  
  
 ドッキング コントロール バーの詳細については、記事を参照してください。[コントロール バー](../../mfc/control-bars.md)、[ツールバー: ドッキング ツールバーとフローティング](../../mfc/docking-and-floating-toolbars.md)、および[フレーム ウィンドウ](../../mfc/frame-windows.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxadv.h  
  
##  <a name="clear"></a>CDockState::Clear  
 格納されているすべてのドッキング情報を削除するには、この関数を呼び出して、`CDockState`オブジェクトです。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 これには、バーがドッキングされているか、バーのサイズと位置があるかどうかだけでなくとが表示されているかどうかが含まれます。  
  
##  <a name="getversion"></a>CDockState::GetVersion  
 格納されているのバージョン番号を取得するには、この関数を呼び出すバー状態です。  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 1 の場合、格納されているバー情報が現在の状態であるバーより古い場合は 2 格納されているバーについては、現在と同じバー状態です。  
  
### <a name="remarks"></a>コメント  
 バージョンのサポートは、新しい永続的なプロパティを追加しを検出し、バーの以前のバージョンで作成された永続的な状態の読み込みができるバーを改訂版を有効します。  
  
##  <a name="loadstate"></a>CDockState::LoadState  
 レジストリから状態情報を取得するには、この関数を呼び出すか。INI ファイルです。  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProfileName`  
 初期化ファイルまたは状態情報が格納されている Windows レジストリ内のキーのセクションの名前を指定する null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 プロファイル名は、アプリケーションのセクションを示します。INI ファイルまたはバーの状態情報を含むレジストリです。 コントロール バーの状態情報をレジストリに保存することができますか。INI ファイルを`SaveState`します。  
  
##  <a name="m_arrbarinfo"></a>CDockState::m_arrBarInfo  
 A`CPtrArray`の状態情報が保存される各コントロール バーの保存された制御バー情報へのポインターの配列であるオブジェクトを`CDockState`オブジェクトです。  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="savestate"></a>後  
 状態情報をレジストリに保存するには、この関数を呼び出すか。INI ファイルです。  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProfileName`  
 初期化ファイルまたは状態情報が格納されている Windows レジストリ内のキーのセクションの名前を指定する null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 プロファイル名は、アプリケーションのセクションを示します。INI ファイルやレジストリを含むコントロール バーの状態情報。 `SaveState`また、現在の画面サイズを保存します。 コントロール バーの情報をレジストリから取得することができますか。INI ファイルを`LoadState`します。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


