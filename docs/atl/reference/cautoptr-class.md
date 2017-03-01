---
title: "CAutoPtr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtr
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 309a3d0ddceab2995c85e156c7db09ddd7edfa86
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptr-class"></a>CAutoPtr クラス
このクラスは、スマート ポインター オブジェクトを表します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CAutoPtr
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ポインター型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](#cautoptr)|コンストラクターです。|  
|[CAutoPtr:: ~ CAutoPtr](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtr::Attach](#attach)|既存のポインターの所有権を取得するには、このメソッドを呼び出します。|  
|[CAutoPtr::Detach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|  
|[CAutoPtr::Free](#free)|指すオブジェクトを削除するには、このメソッドを呼び出して、`CAutoPtr`です。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtr::operator T *](#operator_t_star)|キャスト演算子です。|  
|[CAutoPtr::operator =](#operator_eq)|代入演算子です。|  
|[-> CAutoPtr::operator](#operator_ptr)|メンバーへのポインター演算子です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAutoPtr::m_p](#m_p)|ポインターのデータ メンバー変数です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、作成およびスコープ外にあるときに自動的にリソースを解放して、メモリ リークを防ぐため、スマート ポインターを管理するためのメソッドを提供します。  
  
 さらに、`CAutoPtr`のコピー コンス トラクターと代入演算子所有権を譲渡、ポインターのポインターを変換先のポインターにコピーし、元のポインターを NULL に設定します。 したがって&2; つあることがない`CAutoPtr`は同じポインターを格納する各オブジェクトし、同じポインターを&2; 回削除する可能性を低減これです。  
  
 `CAutoPtr`またポインターのコレクションの作成を簡素化されます。 コレクション クラスを派生して、デストラクターをオーバーライドではなくのコレクションを作成する単純な`CAutoPtr`オブジェクトです。 コレクションが削除されると、`CAutoPtr`オブジェクトがスコープ外に出るし、自動的に削除します。  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)バリアントと同様に動作し、`CAutoPtr`を割り当て、C++ ではなく別のヒープ関数を使用してメモリを解放する点を除き、**新しい**と**削除**演算子。 [出たリソース](../../atl/reference/cautovectorptr-class.md)に似ていますが`CAutoPtr`、唯一の違いが使用されている**new[] をベクトル**と**ベクトル delete[]**メモリ割り当てし、解放をします。  
  
 関連項目[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)と[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)配列またはスマート ポインターのリストが必要な場合です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&74;](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]  
  
##  <a name="a-nameattacha--cautoptrattach"></a><a name="attach"></a>CAutoPtr::Attach  
 既存のポインターの所有権を取得するには、このメソッドを呼び出します。  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 `CAutoPtr` This ポインターの所有権を持つオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ときに、`CAutoPtr`オブジェクトへのポインターの所有権を取得するに自動的に削除されますポインターと、割り当てられているデータ スコープ外になったときにします。 場合[CAutoPtr::Detach](#detach)が呼び出されると、プログラマ再度責任を解放するいずれかの指定されたリソースが割り当てられます。  
  
 デバッグ ビルドで、アサーション エラーが発生場合、 [CAutoPtr::m_p](#m_p)データ メンバーは、現在は、既存の値を指します。 つまり、null はありません。  
  
### <a name="example"></a>例  
 例を参照して、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)します。  
  
##  <a name="a-namecautoptra--cautoptrcautoptr"></a><a name="cautoptr"></a>CAutoPtr::CAutoPtr  
 コンストラクターです。  
  
```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<> 
CAutoPtr(CAutoPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 既存のポインター。  
  
 `TSrc`  
 別の作業で管理されている型`CAutoPtr`、現在のオブジェクトを初期化するために使用します。  
  
### <a name="remarks"></a>コメント  
 `CAutoPtr`オブジェクトの作成は、既存のポインターを使用して、このような場合、ポインターの所有権を転送します。  
  
### <a name="example"></a>例  
 例を参照して、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)します。  
  
##  <a name="a-namedtora--cautoptrcautoptr"></a><a name="dtor"></a>CAutoPtr:: ~ CAutoPtr  
 デストラクターです。  
  
```
~CAutoPtr() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたリソースを解放します。 呼び出し[CAutoPtr::Free](#free)します。  
  
##  <a name="a-namedetacha--cautoptrdetach"></a><a name="detach"></a>CAutoPtr::Detach  
 ポインターの所有権を解放するには、このメソッドを呼び出します。  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターのコピーを返します。  
  
### <a name="remarks"></a>コメント  
 ポインターの所有権を解放、 [CAutoPtr::m_p](#m_p)データ メンバー変数を NULL にし、ポインターのコピーを返します。 呼び出した後**デタッチ**、それを解放するには、プログラマの責任リソースが割り当てられますられる、`CAutoPtr`オブジェクトがある以前とは見なさ reponsibility します。  
  
### <a name="example"></a>例  
 例を参照して、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)します。  
  
##  <a name="a-namefreea--cautoptrfree"></a><a name="free"></a>CAutoPtr::Free  
 指すオブジェクトを削除するには、このメソッドを呼び出して、`CAutoPtr`です。  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>コメント  
 によって指されるオブジェクト、`CAutoPtr`が解放されると、 [CAutoPtr::m_p](#m_p)データ メンバー変数が NULL に設定します。  
  
##  <a name="a-namempa--cautoptrmp"></a><a name="m_p"></a>CAutoPtr::m_p  
 ポインターのデータ メンバー変数です。  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー変数は、ポインターの情報を保持します。  
  
##  <a name="a-nameoperatoreqa--cautoptroperator-"></a><a name="operator_eq"></a>CAutoPtr::operator =  
 代入演算子です。  
  
```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 ポインター。  
  
 `TSrc`  
 クラスの型。  
  
### <a name="return-value"></a>戻り値  
 参照を返す、 **CAutoPtr\< T >**します。  
  
### <a name="remarks"></a>コメント  
 代入演算子をデタッチ、`CAutoPtr`オブジェクトを現在のポインターから新しいポインターのアタッチと`p`、その場所にします。  
  
### <a name="example"></a>例  
 例を参照して、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)します。  
  
##  <a name="a-nameoperatorptra--cautoptroperator--gt"></a><a name="operator_ptr"></a>CAutoPtr::operator-&gt;  
 メンバーへのポインター演算子です。  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 値を返す、 [CAutoPtr::m_p](#m_p)データ メンバー変数です。  
  
### <a name="remarks"></a>コメント  
 この演算子が指すクラスのメソッドを呼び出すを使用して、`CAutoPtr`オブジェクトです。 デバッグ ビルドで、アサーション エラーが発生場合、`CAutoPtr`が NULL を指します。  
  
### <a name="example"></a>例  
 例を参照して、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)します。  
  
##  <a name="a-nameoperatortstara--cautoptroperator-t"></a><a name="operator_t_star"></a>CAutoPtr::operator T *  
 キャスト演算子です。  
  
```  
operator T* () const throw();
```  
  
### <a name="return-value"></a>戻り値  
 クラス テンプレートで定義されたオブジェクト データ型へのポインターを返します。  
  
### <a name="example"></a>例  
 例を参照して、 [CAutoPtr 概要](../../atl/reference/cautoptr-class.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [出たリソース クラス](../../atl/reference/cautovectorptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

