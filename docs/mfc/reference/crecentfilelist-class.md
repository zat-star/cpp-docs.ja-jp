---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecentFileList
- AFXADV/CRecentFileList
- AFXADV/CRecentFileList::CRecentFileList
- AFXADV/CRecentFileList::Add
- AFXADV/CRecentFileList::GetDisplayName
- AFXADV/CRecentFileList::GetSize
- AFXADV/CRecentFileList::ReadList
- AFXADV/CRecentFileList::Remove
- AFXADV/CRecentFileList::UpdateMenu
- AFXADV/CRecentFileList::WriteList
dev_langs:
- C++
helpviewer_keywords:
- files [C++], most recently used
- MRU files
- CRecentFileList class
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5d18daee2e4d809c750ae4654d731888df1db39e
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="crecentfilelist-class"></a>関数のクラス
MRU ファイル リストのコントロールをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CRecentFileList  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRecentFileList::CRecentFileList](#crecentfilelist)|`CRecentFileList` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRecentFileList::Add](#add)|MRU ファイル リストにファイルを追加します。|  
|[CRecentFileList::GetDisplayName](#getdisplayname)|MRU ファイル名のメニューの表示の表示名を提供します。|  
|[CRecentFileList::GetSize](#getsize)|MRU ファイル リスト内のファイルの数を取得します。|  
|[CRecentFileList::ReadList](#readlist)|MRU ファイル リストをレジストリから読み取るか。INI ファイルです。|  
|[CRecentFileList::Remove](#remove)|MRU ファイル リストからファイルを削除します。|  
|[CRecentFileList::UpdateMenu](#updatemenu)|MRU ファイル リストのメニューの表示を更新します。|  
|[CRecentFileList::WriteList](#writelist)|レジストリから MRU ファイル リストを書き込みますか。INI ファイルです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CRecentFileList::operator](#operator_at)|返します。、`CString`指定位置にあるオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 ファイルを追加または MRU ファイル リストから削除、ファイルの一覧の読み取りや、レジストリに書き込まれたことができますか。INI ファイルおよび MRU ファイル リストを表示するメニューを更新することができます。  
  
 最近使用したメニュー項目の詳細については、次を参照してください。  
  
-   サポート技術情報記事 Q243751: HOWTO: MFC アプリケーションで最近使用したメニュー項目に対するコマンド ハンドラーの追加  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CRecentFileList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxadv.h  
  
##  <a name="add"></a>CRecentFileList::Add  
 ファイルを最近使用した MRU ファイル リストに追加します。  
  
```  
virtual void Add(LPCTSTR lpszPathName);

 
virtual void Add(
    LPCTSTR lpszPathName,
    LPCTSTR lpszAppID);

 
void Add(
    IShellItem* pItem,
    LPCTSTR lpszAppID);

 
void Add(
    IShellLink* pLink,
    LPCTSTR lpszAppID);

 
void Add(
    PIDLIST_ABSOLUTE pidl,
    LPCTSTR lpszAppID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 一覧に追加するパス名を指定します。  
  
 `lpszAppID`  
 アプリケーションのアプリケーションのユーザーのモデル ID を指定します。  
  
 `pItem`  
 一覧に追加するシェル項目へのポインターを指定します。  
  
 `pLink`  
 一覧に追加するシェル リンクへのポインターを指定します。  
  
 `pidl`  
 最近使ったドキュメント フォルダーに追加する必要がありますシェル項目の IDLIST を指定します。  
  
### <a name="remarks"></a>コメント  
 ファイル名は、MRU 一覧の先頭に追加されます。 MRU 一覧にファイル名が既に存在する場合は、先頭に移動されます。  
  
##  <a name="crecentfilelist"></a>CRecentFileList::CRecentFileList  
 `CRecentFileList` オブジェクトを構築します。  
  
```  
CRecentFileList(
    UINT nStart,  
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntryFormat,  
    int nSize,  
    int nMaxDispLen = AFX_ABBREV_FILENAME_LEN);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStart`  
 (最近使用された) MRU ファイル リストのメニュー表示内の番号のオフセットします。  
  
 `lpszSection`  
 レジストリまたはアプリケーションのセクションの名前を指します。MRU ファイル リスト INI ファイルは読み取りや書き込みをします。  
  
 `lpszEntryFormat`  
 レジストリまたはアプリケーションの格納されているエントリの名前に使用する書式指定文字列を指します。INI ファイルです。  
  
 `nSize`  
 MRU ファイル リスト内のファイルの最大数。  
  
 `nMaxDispLen`  
 MRU ファイル リスト内のファイル名の表示方法] メニューの [利用可能な文字の最大長。  
  
### <a name="remarks"></a>コメント  
 書式指定文字列を指す`lpszEntryFormat`"%d"の各最近使用した項目のインデックスを置き換えに使用されるを含める必要があります。 たとえば、書式指定文字列は`"file%d"`このという名前を付けると、エントリは`file0`、 `file1`、という具合です。  
  
##  <a name="getdisplayname"></a>CRecentFileList::GetDisplayName  
 MRU 一覧のメニューの表示で使用するため、MRU ファイル リスト内のファイルの表示名を取得します。  
  
```  
virtual BOOL GetDisplayName(
    CString& strName,  
    int nIndex,  
    LPCTSTR lpszCurDir,  
    int nCurDir,  
    BOOL bAtLeastName = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strName`  
 MRU ファイル メニューの一覧に表示される名前のファイルの完全パス。  
  
 `nIndex`  
 MRU ファイル リスト内のファイルの&0; から始まるインデックス。  
  
 *lpszCurDir*  
 現在のディレクトリを保持している文字列。  
  
 *nCurDir*  
 現在のディレクトリの文字列の長さです。  
  
 `bAtLeastName`  
 ゼロ以外の場合を示すファイルのベース名を返すこと、最大表示数を超えた場合でも (として渡される、`nMaxDispLen`パラメーターを`CRecentFileList`コンス トラクター)。  
  
### <a name="return-value"></a>戻り値  
 **FALSE**かどうかがないファイル名の指定したインデックスにある最近使用した MRU ファイル リストです。  
  
### <a name="remarks"></a>コメント  
 ファイルが現在のディレクトリ内にある場合は、関数は、ディレクトリ、ディスプレイの電源を残します。 ファイル名が長すぎる場合、ディレクトリと拡張機能が削除されています。 しない限り表示名は空の文字列に設定、ファイル名が長すぎるまだ場合`bAtLeastName`は&0; 以外。  
  
##  <a name="getsize"></a>CRecentFileList::GetSize  
 MRU ファイル リスト内のファイルの数を取得します。  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のファイルの数は、最近 MRU ファイル リストを使用します。  
  
##  <a name="operator_at"></a>CRecentFileList::operator  
 オーバー ロードされた添字 ( `[]`) 演算子は、1 つを返します`CString`内の&0; から始まるインデックスによって指定された`nIndex`します。  
  
```  
CString& operator[ ](int nindex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 から始まるインデックス、`CString`一連の`CString`秒です。  
  
##  <a name="readlist"></a>CRecentFileList::ReadList  
 最近使用したレジストリまたはアプリケーションの MRU ファイル リストを読み取ります。INI ファイルです。  
  
```  
virtual void ReadList();
```  
  
##  <a name="remove"></a>CRecentFileList::Remove  
 MRU ファイル リストからファイルを削除します。  
  
```  
virtual void Remove(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 最近使用した MRU ファイル リストから削除するファイルの&0; から始まるインデックス。  
  
##  <a name="updatemenu"></a>CRecentFileList::UpdateMenu  
 MRU ファイル リストのメニューの表示を更新します。  
  
```  
virtual void UpdateMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、 [CCmdUI](../../mfc/reference/ccmdui-class.md)最近使用した MRU ファイル リスト メニューのオブジェクト。  
  
##  <a name="writelist"></a>CRecentFileList::WriteList  
 最近使用した MRU ファイル リスト、アプリケーションのレジストリに書き込みます。INI ファイルです。  
  
```  
virtual void WriteList();
```  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)




