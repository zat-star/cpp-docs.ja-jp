---
title: "CSimpleException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException class
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5612d76a2351b9898b8ffe082844686d21fcd7a0
ms.lasthandoff: 02/24/2017

---
# <a name="csimpleexception-class"></a>CSimpleException クラス
このクラスは、リソース クリティカルな MFC 例外の基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|発生したエラーに関するテキストを提供します。|  
  
## <a name="remarks"></a>コメント  
 `CSimpleException`リソース クリティカルな MFC 例外の基底クラスは、所有権と、エラー メッセージの初期化を処理します。 次のクラスを使用して`CSimpleException`その基本クラスとして。  
  
|||  
|-|-|  
|[関数のクラス](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|  
|[行わないクラス](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|  
|[関数のクラス](../../mfc/reference/cresourceexception-class.md)|Windows リソース見つからないか、または不可能|  
|[チェック クラス](../../mfc/reference/cuserexception-class.md)|リソースを示す例外が見つかりませんでした。|  
|[CInvalidArgException クラス](../../mfc/reference/cinvalidargexception-class.md)|無効な引数を示す例外|  
  
 `CSimpleException`抽象基本クラスは、宣言することはできません、`CSimpleException`オブジェクトに直接します。 代わりに、前の表に示すなどの派生オブジェクトを宣言する必要があります。 派生クラスを宣言する場合は、モデルとして前のクラスを使用します。  
  
 詳細については、次を参照してください。、 [CException クラス](../../mfc/reference/cexception-class.md)トピックと[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="csimpleexception"></a>CSimpleException::CSimpleException  
 コンストラクターです。  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAutoDelete`  
 指定**TRUE**場合のメモリを`CSimpleException`オブジェクトがヒープに割り当てられています。 これにより、`CSimpleException`ときに削除するオブジェクト、**削除**例外を削除するメンバー関数が呼び出されます。 指定**FALSE**場合、`CSimpleException`オブジェクトがスタック上またはグローバル オブジェクトです。 ここで、`CSimpleException`オブジェクトはできない時に削除、**削除**メンバー関数が呼び出されます。  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接呼び出す必要は通常ことはありません。 例外をスローする関数のインスタンスを作成する必要があります、 `CException`-クラスを派生し、呼び出すコンス トラクター、またはそれが、MFC のいずれかの使用をスローする関数など[AfxThrowFileException](exception-processing.md#afxthrowfileexception)、定義済みの型をスローします。  
  
##  <a name="geterrormessage"></a>CSimpleException::GetErrorMessage  
 発生したエラーに関するテキストを提供するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszError`  
 エラー メッセージを受信するバッファーへのポインター。  
  
 `nMaxError`  
 バッファーに保持できる文字の最大数、 **NULL**ターミネータです。  
  
 `pnHelpContext`  
 アドレス、 **UINT**ヘルプ コンテキスト ID を受信します。 場合**NULL**ID は返されません。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 (ゼロ) の場合、エラー メッセージ テキストは使用できます。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [例外処理](../../mfc/exception-handling-in-mfc.md)




