---
title: "コレクション クラスのヘルパー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes, helper functions
- helper functions collection class
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
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
ms.openlocfilehash: d2649ef9c8b0320a94ec28a2341baa0f768b07d0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="collection-class-helpers"></a>コレクション クラスのヘルパー
コレクション クラス`CMap`、 `CList`、および`CArray`を比較する、コピー、および要素をシリアル化するために、template 宣言されたグローバルなヘルパー関数を使用します。 基づくクラスの実装の一部として`CMap`、 `CList`、および`CArray`マップ、リスト、または配列に格納されたデータの種類に合うように、必要に応じて、これらの関数をオーバーライドする必要があります。 などのヘルパー関数を上書きする方法について`SerializeElements`、記事を参照して[コレクション: タイプ セーフなコレクションを作成する方法](../../mfc/how-to-make-a-type-safe-collection.md)します。 なお**ConstructElements**と**DestructElements**は廃止されました。  
  
 Microsoft Foundation Class ライブラリは、afxtempl.h コレクション クラスをカスタマイズするための次のグローバル関数を提供します。  
  
### <a name="collection-class-helpers"></a>コレクション クラスのヘルパー  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|要素が同じであるかどうかを示します。|  
|[CopyElements](#copyelements)|別の&1; つの配列から要素をコピーします。|  
|[DumpElements](#dumpelements)|ストリーム指向の診断出力を提供します。|  
|[HashKey](#hashkey)|ハッシュ キーを計算します。|  
|[SerializeElements](#serializeelements)|保存またはアーカイブからの要素を取得します。|  
  
##  <a name="compareelements"></a>CompareElements  
 によって直接と呼ばれる [CList::Find] (clist class.md #not_found.md #clist__find と間接的に[cmap__lookup](cmap-class.md#lookup)と[cmap__operator](cmap-class.md#operator_at)します。  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 比較する最初の要素の型。  
  
 `pElement1`  
 比較する最初の要素へのポインター。  
  
 `ARG_TYPE`  
 比較する&2; 番目の要素の型。  
  
 `pElement2`  
 比較する&2; 番目の要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 によって指されるオブジェクトの場合は 0 以外`pElement1`が指すオブジェクトと等しい`pElement2`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 `CMap`使用を呼び出し、`CMap`テンプレート パラメーター*キー*と`ARG_KEY`です。  
  
 既定の実装の比較の結果を返す* \*pElement1*と* \*pElement2*します。 アプリケーションに適した方法で要素を比較できるように、この関数をオーバーライドします。  
  
 C++ 言語には、比較演算子が定義されて ( `==`) 単純型の ( `char`、 `int`、 **float**など) が次のクラスと構造体の比較演算子を定義しません。 使用する場合は、 `CompareElements` 、それを使用するコレクション クラスのいずれかをインスタンス化する必要がありますか比較演算子を定義する、または、オーバー ロードまたは`CompareElements`バージョンに適切な値を取得します。  
  
### <a name="requirements"></a>要件  
   **ヘッダー:** afxtempl.h   
  
##  <a name="copyelements"></a>CopyElements  
 この関数によって直接[CArray::Append](carray-class.md#append)と[CArray::Copy](carray-class.md#copy)します。  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 コピーする要素の型を指定するテンプレート パラメーター。  
  
 `pDest`  
 要素のコピー先へのポインター。  
  
 `pSrc`  
 コピーする要素のソースへのポインター。  
  
 `nCount`  
 コピーされる要素の数。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、単純な代入演算子を使用して ( ** = ** )、コピー操作を実行します。 コピーされた型がオーバー ロードされた演算子 =、既定の実装は、ビットごとのコピーを実行します。  
  
 これと他のヘルパー関数を実装する方法の詳細については、記事を参照してください。[コレクション: タイプ セーフなコレクションを作成する方法](../how-to-make-a-type-safe-collection.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxtempl.h  
  
##  <a name="dumpelements"></a>DumpElements  
 オーバーライドされた場合、コレクションの要素のテキスト形式のストリーム指向の診断出力を提供します。  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>パラメーター  
 `dc`  
 要素をダンプするためのコンテキストをダンプします。  
  
 *型*  
 要素の型を指定するテンプレート パラメーター。  
  
 `pElements`  
 ダンプする要素へのポインター。  
  
 `nCount`  
 ダンプする要素の数。  
  
### <a name="remarks"></a>コメント  
 **CArray::Dump**、 **CList::Dump**、および**CMap::Dump**ダンプの深さが 0 より大きい場合は、この関数呼び出しです。  
  
 既定の実装では、何も行われません。 コレクションの要素がから派生した場合`CObject`、オーバーライドした関数では、コレクションの要素を反復処理する通常の呼び出し`Dump`ターンの各要素に対してです。  
  

### <a name="requirements"></a>要件  
  **ヘッダー** afxtempl.h  
  
##  <a name="hashkey"></a>HashKey  
 指定したキーのハッシュ値を計算します。  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_KEY`  
 マップ キーにアクセスするために使用するデータ型を指定するテンプレート パラメーター。  
  
 `key`  
 ハッシュ値が計算されるキーです。  
  
### <a name="return-value"></a>戻り値  
 キーのハッシュ値。  
  
### <a name="remarks"></a>コメント  
 この関数によって直接[CMap::RemoveKey](cmap-class.md#removekey)と間接的に[CMap::Lookup](cmap-class.md#lookup)と[CMap::Operator](cmap-class.md#operator_at)します。
  
 既定の実装では、ハッシュ値を作成脱却しつつ`key`を&4; つの位置。 アプリケーションに適したハッシュ値を返すように、この関数をオーバーライドします。  
  
### <a name="example"></a>例
 ```cpp  
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number 
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
 ```
 
### <a name="requirements"></a>要件  
  **ヘッダー** afxtempl.h 
  
##  <a name="serializeelements"></a>SerializeElements  
 [CArray](carray-class.md)、 [CList](clist-class.md)、および[メンバー](cmap-class.md)要素にシリアル化には、この関数を呼び出します。  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 要素の型を指定するテンプレート パラメーター。  
  
 `ar`  
 アーカイブするアーカイブ オブジェクト。  
  
 `pElements`  
 アーカイブされる要素へのポインター。  
  
 `nCount`  
 アーカイブ対象の要素の数  
  
### <a name="remarks"></a>コメント  
 既定の実装は、ビットごとの読み取りまたは書き込み。  
  
 これと他のヘルパー関数を実装する方法の詳細については、記事を参照してください。[コレクション: タイプ セーフなコレクションを作成する方法](../how-to-make-a-type-safe-collection.md)します。  
  
### <a name="example"></a>例  
 記事の例を参照して[コレクション: タイプ セーフなコレクションを作成する方法](../how-to-make-a-type-safe-collection.md)します。  
 
### <a name="requirements"></a>要件  
  **ヘッダー** afxtempl.h 
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [メンバー クラス](cmap-class.md)   
 [CList クラス](clist-class.md)   
 [CArray クラス](carray-class.md)
