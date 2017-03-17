---
title: "CMemFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
dev_langs:
- C++
helpviewer_keywords:
- memory files
- CMemFile class
- temporary files, memory files
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9851e050b05ac129e5e498c7ea99dfedddc79e54
ms.lasthandoff: 02/24/2017

---
# <a name="cmemfile-class"></a>CMemFile クラス
[CFile](../../mfc/reference/cfile-class.md)-をメモリ上のファイルをサポートするクラスを派生します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMemFile : public CFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMemFile::CMemFile](#cmemfile)|メモリ ファイル オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMemFile::Attach](#attach)|メモリ ブロックをアタッチ`CMemFile`します。|  
|[CMemFile::Detach](#detach)|メモリ ブロックをデタッチ`CMemFile`デタッチされたメモリ ブロックへのポインターを返します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMemFile::Alloc](#alloc)|メモリ割り当ての動作を変更するためにオーバーライドします。|  
|[CMemFile::Free](#free)|メモリの割り当て解除の動作を変更するためにオーバーライドします。|  
|[CMemFile::GrowFile](#growfile)|ファイルを拡張するときの動作を変更するためにオーバーライドします。|  
|[CMemFile::Memcpy](#memcpy)|ファイルを読み書きするときに、メモリ コピー動作を変更するためにオーバーライドします。|  
|[CMemFile::Realloc](#realloc)|メモリ割り当ての変更動作を変更するためにオーバーライドします。|  
  
## <a name="remarks"></a>コメント  
 これらのメモリ ファイルは、ファイルはディスクではなく RAM に保存する点を除いて、ディスク ファイルと同様に動作します。 メモリ ファイルは高速に一時的な記憶域または実際のバイト数を転送するために役立ちます。 または、独立したプロセス間でオブジェクトをシリアル化します。  
  
 `CMemFile`オブジェクトは、独自のメモリを自動的に割り当てることができますか、独自のメモリ ブロックを割り当てることができます、`CMemFile`を呼び出してオブジェクト[アタッチ](#attach)します。 いずれの場合メモリ ファイルを自動的に拡張用のメモリが割り当てられている`nGrowBytes`-場合分ずつ`nGrowBytes`が&0; でないです。  
  
 破棄後に、メモリ ブロックが自動的に削除されます、`CMemFile`オブジェクトのメモリが本来によって割り当てられたかどうか、`CMemFile`オブジェクト。 それ以外の場合、ユーザーは、オブジェクトに関連付けられているメモリを解放する担当します。  
  
 切断するときに提供されるポインターを通じてメモリ ブロックにアクセスすることができます、`CMemFile`を呼び出してオブジェクト[デタッチ](#detach)します。  
  
 最も一般的な用途`CMemFile`を作成するには、`CMemFile`しオブジェクトから呼び出すことによって使用[CFile](../../mfc/reference/cfile-class.md)メンバー関数。 作成することに注意してください、`CMemFile`自動的に開きます。 呼び出さない[CFile::Open](../../mfc/reference/cfile-class.md#open)、ディスク ファイルにのみ使用されます。 `CMemFile`ディスク ファイルをデータ メンバーを使用しない`CFile::m_hFile`は使用されません。  
  
 `CFile`メンバー関数[複製](../../mfc/reference/cfile-class.md#duplicate)、 [LockRange](../../mfc/reference/cfile-class.md#lockrange)、および[UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)は適用されていない`CMemFile`します。 これらの関数を呼び出した場合、`CMemFile`オブジェクトの取得は、[行わない](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 `CMemFile`ランタイム ライブラリ関数を使用して[malloc](../../c-runtime-library/reference/malloc.md)、 [realloc](../../c-runtime-library/reference/realloc.md)、および[無料](../../c-runtime-library/reference/free.md)割り当てるには、再割り当て、およびメモリと、組み込みの割り当てを解除[memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)ブロックの読み取りまたは書き込み時に、メモリをコピーします。 この動作または動作を変更するようにかどうかと`CMemFile`、ファイルの拡張からクラスを派生`CMemFile`と適切な関数をオーバーライドします。  
  
 詳細については`CMemFile`、記事を参照して[MFC のファイル](../../mfc/files-in-mfc.md)と[メモリ管理 (MFC)](../../mfc/memory-management.md)を参照してくださいと[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="alloc"></a>CMemFile::Alloc  
 この関数は`CMemFile`メンバー関数。  
  
```  
virtual BYTE* Alloc(SIZE_T nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 割り当てるメモリのバイト数。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックへのポインターまたは**NULL**場合は、割り当てが失敗します。  
  
### <a name="remarks"></a>コメント  
 独自のメモリ割り当てを実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合はおそらくにしておくオーバーライド[Free](#free)と[Realloc](#realloc)もします。  
  
 既定の実装は、ランタイム ライブラリ関数を使用して[malloc](../../c-runtime-library/reference/malloc.md)メモリを割り当てられません。  
  
##  <a name="attach"></a>CMemFile::Attach  
 メモリ ブロックをアタッチするには、この関数を呼び出す`CMemFile`します。  
  
```  
void Attach(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpBuffer`  
 アタッチされているバッファーへのポインター`CMemFile`します。  
  
 `nBufferSize`  
 バッファーのサイズをバイト単位で指定する整数。  
  
 `nGrowBytes`  
 バイト単位でメモリ割り当てインクリメントします。  
  
### <a name="remarks"></a>コメント  
 これにより、`CMemFile`メモリ ファイルとしてのメモリ ブロックを使用します。  
  
 場合`nGrowBytes`は 0、`CMemFile`にファイルの長さを設定`nBufferSize`します。 つまり、このメモリ ブロック内のデータに割り当てられる前に`CMemFile`ファイルとして使用されます。 この方法で作成されたメモリ ファイルは拡張できません。  
  
 ファイルが拡張できない場合、以降は、発生しないように注意する`CMemFile`ファイルを拡張しようとします。 などを呼び出さないで、`CMemFile`のオーバーライド[CFile:Write](../../mfc/reference/cfile-class.md#write)に末尾を越えて書き込みまたは呼び出さないで[CFile:SetLength](../../mfc/reference/cfile-class.md#setlength)を超える長さの`nBufferSize`です。  
  
 場合`nGrowBytes`は 0 より大きく、`CMemFile`アタッチしたメモリ ブロックの内容は無視されます。 スクラッチを使用して、メモリ ファイルの内容を記述する必要があります、`CMemFile`のオーバーライド`CFile::Write`します。 ファイルの末尾を超えて書き込みまたはを呼び出して、ファイルを拡張しようとすると、`CMemFile`のオーバーライド`CFile::SetLength`、`CMemFile`単位でメモリの割り当てを成長`nGrowBytes`します。 メモリの割り当ての成長にメモリ ブロックを渡す場合は失敗**アタッチ**と互換性のあるメソッドを使用して割り当てられていない[アロケーション](#alloc)です。 既定の実装と互換性がある`Alloc`、ランタイム ライブラリ関数でメモリを割り当てる必要があります[malloc](../../c-runtime-library/reference/malloc.md)または[calloc](../../c-runtime-library/reference/calloc.md)します。  
  
##  <a name="cmemfile"></a>CMemFile::CMemFile  
 最初のオーバー ロードは、空のメモリのファイルを開きます。  
  
```  
CMemFile(UINT nGrowBytes = 1024);

 
CMemFile(
    BYTE* lpBuffer,  
    UINT nBufferSize,  
    UINT nGrowBytes = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGrowBytes`  
 バイト単位でメモリ割り当てインクリメントします。  
  
 *lpBuffe*r  
 サイズの情報を受け取るバッファーへのポインター`nBufferSize`します。  
  
 `nBufferSize`  
 バイト単位で、ファイル バッファーのサイズを指定する整数。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターによって、ファイルが開かれていると、呼び出す必要はありません[CFile::Open](../../mfc/reference/cfile-class.md#open)します。  
  
 最初のコンス トラクターを使用して、すぐと呼ばれる場合と同じ&2; つ目のオーバー ロードは、動作[アタッチ](#attach)同じパラメーターを使用します。 参照してください**アタッチ**詳細です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCFiles&#36;](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]  
  
##  <a name="detach"></a>CMemFile::Detach  
 によって使用されているメモリ ブロックへのポインターを取得するには、この関数を呼び出す`CMemFile`します。  
  
```  
BYTE* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 メモリ ファイルの内容を保持するメモリ ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数も閉じ、`CMemFile`です。 メモリ ブロックを再アタッチできる`CMemFile`を呼び出して[アタッチ](#attach)します。 ファイルを再アタッチし、データを使用する場合を呼び出す必要があります[結び付けてその中](../../mfc/reference/cfile-class.md#getlength)を呼び出す前にファイルの長さを取得する**デタッチ**します。 メモリ ブロックをアタッチする場合は、`CMemFile`のデータを使用できるように ( `nGrowBytes` 0 = =)、メモリ ファイルを拡張することはできませんし、します。  
  
##  <a name="free"></a>CMemFile::Free  
 この関数は`CMemFile`メンバー関数。  
  
```  
virtual void Free(BYTE* lpMem);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMem`  
 解放するメモリへのポインター*します。*  
  
### <a name="remarks"></a>コメント  
 カスタム メモリの解放を実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合はおそらくにしておくオーバーライド[アロケーション](#alloc)と[Realloc](#realloc)もします。  
  
##  <a name="growfile"></a>CMemFile::GrowFile  
 この関数は、いくつかの`CMemFile`メンバー関数。  
  
```  
virtual void GrowFile(SIZE_T dwNewLen);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwNewLen`  
 メモリ ファイルの新しいサイズ。  
  
### <a name="remarks"></a>コメント  
 変更する場合にオーバーライドできる方法`CMemFile`そのファイルを拡張します。 既定の実装[Realloc](#realloc)既存のブロックを拡張する (または[アロケーション](#alloc)メモリ ブロックを作成する) の倍数でメモリを割り当て、`nGrowBytes`コンス トラクターで指定された値または[アタッチ](#attach)呼び出します。  
  
##  <a name="memcpy"></a>CMemFile::Memcpy  
 この関数は、`CMemFile`のオーバーライド[:read](../../mfc/reference/cfile-class.md#read)と[CFile::Write](../../mfc/reference/cfile-class.md#write)メモリ ファイル間でデータを転送します。  
  
```  
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,  
    const BYTE* lpMemSource,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMemTarget`  
 ソースのメモリがコピーされるメモリ ブロックへのポインター。  
  
 `lpMemSource`  
 元のメモリ ブロックへのポインター。  
  
 `nBytes`  
 コピー対象のバイト数。  
  
### <a name="return-value"></a>戻り値  
 `lpMemTarget` のコピー。  
  
### <a name="remarks"></a>コメント  
 方法を変更する場合は、この関数をオーバーライドする`CMemFile`はメモリをコピーします。  
  
##  <a name="realloc"></a>CMemFile::Realloc  
 この関数は`CMemFile`メンバー関数。  
  
```  
virtual BYTE* Realloc(
    BYTE* lpMem,  
    SIZE_T nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMem`  
 再割り当てできるメモリ ブロックへのポインター。  
  
 `nBytes`  
 メモリ ブロックの新しいサイズ。  
  
### <a name="return-value"></a>戻り値  
 再割り当て (され、場合によって移動)、メモリ ブロックへのポインターまたは**NULL**再割り当てが失敗した場合。  
  
### <a name="remarks"></a>コメント  
 カスタム メモリ割り当ての変更を実装するには、この関数をオーバーライドします。 この関数をオーバーライドする場合はおそらくにしておくオーバーライド[アロケーション](#alloc)と[Free](#free)もします。  
  
## <a name="see-also"></a>関連項目  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




