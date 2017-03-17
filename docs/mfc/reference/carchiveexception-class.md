---
title: "CArchiveException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], serialization
- serialization [C++], exceptions
- CArchiveException class
- exceptions [C++], archive
- archive exceptions [C++]
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: e927bea5b8d9e6dbaafb191f6c3bdcf0f0d076cc
ms.lasthandoff: 02/24/2017

---
# <a name="carchiveexception-class"></a>CArchiveException クラス
シリアル化の例外条件を表します  
  
## <a name="syntax"></a>構文  
  
```  
class CArchiveException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CArchiveException::CArchiveException](#carchiveexception)|`CArchiveException` オブジェクトを構築します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CArchiveException::m_cause](#m_cause)|例外の原因を示します。|  
|[CArchiveException::m_strFileName](#m_strfilename)|この例外の状態のファイルの名前を指定します。|  
  
## <a name="remarks"></a>コメント  
 `CArchiveException`クラスには、例外の原因を示すパブリック データ メンバーが含まれています。  
  
 `CArchiveException`オブジェクトが構築され、内でスロー [CArchive](../../mfc/reference/carchive-class.md)メンバー関数。 これらのオブジェクトのスコープ内にアクセスすることができます、**キャッチ**式です。 原因コードは、オペレーティング システムから独立します。 例外の処理の詳細については、次を参照してください。[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="carchiveexception"></a>CArchiveException::CArchiveException  
 構築、`CArchiveException`の値を格納するオブジェクト`cause`オブジェクトです。  
  
```  
CArchiveException(
    int cause = CArchiveException::none,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `cause`  
 例外の原因を示す列挙型の変数。 列挙子の一覧は、次を参照してください。、[は](#m_cause)データ メンバーです。  
  
 `lpszArchiveName`  
 名前を含む文字列を指す、`CArchive`オブジェクトの例外が発生します。  
  
### <a name="remarks"></a>コメント  
 作成することができます、`CArchiveException`グローバル関数のヒープ上のオブジェクトし自分でスローさせたり[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)処理を行います。  
  
 このコンス トラクターを直接使用しないでください。代わりに、グローバル関数を呼び出す`AfxThrowArchiveException`します。  
  
##  <a name="m_cause"></a>CArchiveException::m_cause  
 例外の原因を指定します。  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>コメント  
 このデータ メンバーは `int` 型のパブリック変数です。 その値は、`CArchiveException`列挙型。 列挙子とその意味は次のとおりです。  
  
- **CArchiveException::none**エラーが発生していません。  
  
- **CArchiveException::genericException**特定できないエラーです。  
  
- **CArchiveException::readOnly**の読み込みの開かれたアーカイブに書き込もうとしました。  
  
- **CArchiveException::endOfFile**オブジェクトを読み取り中に最後のファイルに達しました。  
  
- **CArchiveException::writeOnly**を格納するために開かれたアーカイブから読み取ろうとしました。  
  
- **CArchiveException::badIndex**ファイル形式が無効です。  
  
- **CArchiveException::badClass**は無効な型のオブジェクトにオブジェクトを読み取ろうとしました。  
  
- **CArchiveException::badSchema**クラスの異なるバージョンのオブジェクトを読み込もうとしました。  
  
    > [!NOTE]
    >  これらの `CArchiveException` 原因列挙子は、`CFileException` 原因列挙子とは異なります。  
  
    > [!NOTE]
    > **CArchiveException::generic**は使用されなくなりました。 使用**代わり**代わりにします。 場合**汎用**アプリケーションで使用され、ビルドは/clr ではエラーが発生する構文は、簡単に解読できません。  
  
##  <a name="m_strfilename"></a>CArchiveException::m_strFileName  
 この例外の状態のファイルの名前を指定します。  
  
```  
CString m_strFileName;  
```  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CArchive クラス](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)   
 [例外の処理](../../mfc/reference/exception-processing.md)


