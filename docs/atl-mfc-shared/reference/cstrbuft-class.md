---
title: "CStrBufT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CStrBufT<TCharType>
- ATL.CStrBufT
- CStrBufT
- ATL::CStrBufT
- ATL.CStrBufT<TCharType>
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: 17
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
ms.openlocfilehash: 2eb551d2db029de88aa9c1b456c44609b7fc0922
ms.lasthandoff: 02/24/2017

---
# <a name="cstrbuft-class"></a>CStrBufT クラス
このクラスは、自動リソースのクリーンアップを`GetBuffer`と`ReleaseBuffer`、既存の呼び出し`CStringT`オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```
template<typename TCharType>
class CStrBufT
```  
  
#### <a name="parameters"></a>パラメーター  
 *TCharType*  
 文字型、`CStrBufT`クラスです。 次のいずれかの値を指定します。  
  
- `char`(の ANSI 文字列)  
  
- `wchar_t`(する Unicode 文字の文字列)  
  
- **TCHAR** (の ANSI および Unicode 文字列)  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`PCXSTR`|定数文字列へのポインター。|  
|`PXSTR`|文字列へのポインター。|  
|`StringType`|このクラス テンプレートの特殊化で操作するためのバッファーは、文字列型です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](#cstrbuft)|文字列バッファー オブジェクトのコンス トラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStrBufT::SetLength](#setlength)|関連付けられている文字列オブジェクトの文字バッファーの長さを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|取得、 **const**関連付けられている文字列オブジェクトの文字バッファーへのポインター。|  
|[CStrBufT::operator PXSTR](#operator_pxstr)|関連付けられている文字列オブジェクトの文字バッファーへのポインターを取得します。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[CStrBufT::AUTO_LENGTH](#auto_length)|リリース時に、文字列の長さを自動的に決定します。|  
|[CStrBufT::SET_LENGTH](#set_length)|GetBuffer 時に文字列オブジェクトの長さを設定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、呼び出しに置き換えることのラッパー クラスとして使用が[GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)と[ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)、または[GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)と`ReleaseBuffer`です。  
  
 ヘルパー クラスとして設計された`CStrBufT`について心配することがなく、文字列オブジェクトの文字バッファーを使用する開発者にとって便利な方法を提供またはを呼び出すタイミング`ReleaseBuffer`します。 これは、ラッパー オブジェクトが例外または終了する複数のコード パスの場合に自然にスコープから外れるので可能文字列リソースを解放するデストラクターを引き起こしています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpstr.h  
  
##  <a name="a-nameautolengtha--cstrbuftautolength"></a><a name="auto_length"></a>CStrBufT::AUTO_LENGTH  
 リリース時に、文字列の長さを自動的に決定します。  
  
```
static const DWORD AUTO_LENGTH = 0x01;
```  
  
### <a name="remarks"></a>コメント  
 リリース時に、文字列の長さを自動的に決定します。 Null で終わる文字列でなければなりません。  
  
##  <a name="a-namecstrbufta--cstrbuftcstrbuft"></a><a name="cstrbuft"></a>CStrBufT::CStrBufT  
 バッファー オブジェクトを構築します。  
  
```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 バッファーに関連付けられている文字列オブジェクト。 通常、開発者がの定義済みの typedef を使用**CStrBuf** ( **TCHAR**バリアント型)、 **CStrBufA** (`char`バリエーション) と**CStrBufW** (`wchar_t`バリアント型)。  
  
 *nMinLength*  
 文字バッファーの最小長。  
  
 `dwFlags`  
 文字列の長さが自動的に決定されているかどうかを判断します。 次のいずれかの値を指定します。  
  
- **AUTO_LENGTH**文字列の長さが自動的に決定するときに[CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer)が呼び出されます。 Null で終わる文字列でなければなりません。 既定値です。  
  
- **SET_LENGTH**場合、文字列の長さが設定[CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)が呼び出されます。  
  
### <a name="remarks"></a>コメント  
 関連付けられている文字列オブジェクトの文字列バッファーを作成します。 構築時に、 [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)または[CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)が呼び出されます。  
  
 コピー コンス トラクターは`private`です。  
  
##  <a name="a-nameoperatorpcxstra--cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a>CStrBufT::operator PCXSTR  
 関連付けられている文字列オブジェクトを C スタイルの文字列として格納される文字に直接アクセスします。  
  
```  
operator PCXSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列のデータを指すポインター。  
  
### <a name="remarks"></a>コメント  
 この関数では、文字列オブジェクトの文字バッファーへのポインターを返します。 このポインターでは、文字列オブジェクトの内容を変更することはできません。  
  
##  <a name="a-nameoperatorpxstra--cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a>CStrBufT::operator PXSTR  
 関連付けられている文字列オブジェクトを C スタイルの文字列として格納される文字に直接アクセスします。  
  
```
operator PXSTR() throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列のデータを指すポインター。  
  
### <a name="remarks"></a>コメント  
 この関数では、文字列オブジェクトの文字バッファーへのポインターを返します。 開発者は、このポインターを持つ文字列オブジェクトの内容を変更できます。  
  
##  <a name="a-namepcxstra--cstrbuftpcxstr"></a><a name="pcxstr"></a>CStrBufT::PCXSTR  
 定数文字列へのポインター。  
  
```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```  
  
##  <a name="a-namepxstra--cstrbuftpxstr"></a><a name="pxstr"></a>CStrBufT::PXSTR  
 文字列へのポインター。  
  
```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```  
  
##  <a name="a-namesetlengtha--cstrbuftsetlength"></a><a name="set_length"></a>CStrBufT::SET_LENGTH  
 文字列オブジェクトの長さを設定`GetBuffer`時間です。  
  
```
static const DWORD SET_LENGTH = 0x02;
```  
  
### <a name="remarks"></a>コメント  
 GetBuffer 時に、文字列オブジェクトの長さを設定します。  
  
 かどうかを[CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer)と[CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength)文字列バッファー オブジェクトの構築時に呼び出されます。  
  
##  <a name="a-namesetlengtha--cstrbuftsetlength"></a><a name="setlength"></a>CStrBufT::SetLength  
 文字バッファーの長さを設定します。  
  
```
void SetLength(int nLength);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLength`  
 文字列オブジェクトの文字バッファーの新しい長さ。  
  
> [!NOTE]
>  コンス トラクターで指定された最小バッファーの長さ以下である必要があります`CStrBufT`します。  
  
### <a name="remarks"></a>コメント  
 バッファー オブジェクトで表される文字列の長さを設定するには、この関数を呼び出します。  
  
##  <a name="a-namestringtypea--cstrbuftstringtype"></a><a name="stringtype"></a>CStrBufT::StringType  
 このクラス テンプレートの特殊化で操作するためのバッファーは、文字列型です。  
  
```
typedef CSimpleStringT<TCharType> StringType;
```  
  
### <a name="remarks"></a>コメント  
 **TCharType**クラス テンプレートの特定に使用する文字の種類します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)



