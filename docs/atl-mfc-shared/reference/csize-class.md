---
title: "CSize クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
dev_langs:
- C++
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
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
ms.openlocfilehash: 96905d916dfde8f8a7bf8131a280ae7ccfe511d8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="csize-class"></a>CSize クラス
Windows の [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) 構造体と同様に、相対座標や位置を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSize : public tagSIZE 
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSize::CSize](#csize)|`CSize` オブジェクトを構築します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSize::operator-](#operator_-)|2 つのサイズを減算します。|  
|[CSize::operator! =](#operator_neq)|間の非等値チェック`CSize`とサイズ。|  
|[CSize::operator +](#operator_add)|2 つのサイズを追加します。|  
|[CSize::operator + = 演算子](#operator_add_eq)|追加することをサイズ`CSize`します。|  
|[CSize::operator =](#operator_-_eq)|サイズを減算`CSize`します。|  
|[CSize::operator = =](#operator_eq_eq)|等しいかどうかをチェック`CSize`とサイズ。|  
  
## <a name="remarks"></a>コメント  
 このクラスから派生、**サイズ**構造体。 つまり、渡すことができます、`CSize`の呼び出しをパラメーターで、**サイズ**とのデータ メンバー、**サイズ**構造のアクセス可能なデータ メンバーである`CSize`です。  
  
 **Cx**と**cy**のメンバー**サイズ**(と`CSize`) はパブリックです。 さらに、`CSize`を操作するメンバー関数を実装して、**サイズ**構造体。  
  
> [!NOTE]
>  詳細については、ユーティリティ クラスを共有 (のように`CSize`) を参照してください[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagSIZE`  
  
 `CSize`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltypes.h  
  
##  <a name="csize"></a>CSize::CSize  
 `CSize` オブジェクトを構築します。  
  
```  
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 *initCX*  
 セット、 **cx**のメンバー、`CSize`です。  
  
 *initCY*  
 セット、 **cy**のメンバー、`CSize`です。  
  
 `initSize`  
 [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または`CSize`オブジェクトの初期化に使用される`CSize`します。  
  
 `initPt`  
 [ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`オブジェクトの初期化に使用される`CSize`します。  
  
 `dwSize`  
 `DWORD`初期化に使用される`CSize`します。 下位ワードは、 **cx**メンバーと上位ワードは、 **cy**メンバーです。  
  
### <a name="remarks"></a>コメント  
 引数を指定しない場合**cx**と**cy**&0; に初期化されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&97;](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>CSize::operator = =  
 2 つのサイズに等しいかどうかを確認します。  
  
```   
BOOL operator==(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>コメント  
 サイズが等しい場合は 0 以外を返します。、0 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&98;](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]  
  
##  <a name="operator_neq"></a>CSize::operator! =  
 2 つのサイズには、非等値を確認します。  
  
```   
BOOL operator!=(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>コメント  
 サイズが等しくない場合は 0 以外を返します。 それ以外の場合に 0 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#99;](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>CSize::operator + = 演算子  
 次のようなサイズを追加`CSize`します。  
  
```   
void operator+=(SIZE size) throw(); 
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#100;](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>CSize::operator =  
 このサイズを減算`CSize`します。  
  
```   
void operator-=(SIZE size) throw(); 
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&101;](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]  
  
##  <a name="operator_add"></a>CSize::operator +  
 これらの演算子は、これを追加`CSize`値パラメーターの値にします。  
  
```   
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw(); 
```  
  
### <a name="remarks"></a>コメント  
 次の各演算子の説明を参照してください。  
  
- **operator + (** `size` **)**この操作は、2 つ追加`CSize`値。  
  
- **演算子 + (** `point` **)**この操作のオフセット (移動)、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)(または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) この値`CSize`値。 **Cx**と**cy** this のメンバー`CSize`値に追加されます、 **x**と**y**のデータ メンバー、**ポイント**値。 バージョンと類似している[CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add)を受け取り、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)パラメーター。  
  
- **演算子 + (** `lpRect` **)**この操作のオフセット (移動)、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) (または[CRect](../../atl-mfc-shared/reference/crect-class.md)) この値`CSize`値。 **Cx**と**cy** this のメンバー`CSize`値に追加されます、**左**、**上部**、**右**、および**下部**のデータ メンバー、`RECT`値。 バージョンと類似している[CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add)を受け取り、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)パラメーター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&102;](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]  
  
##  <a name="operator_-"></a>CSize::operator-  
 この最初の&3; つの演算子が減算`CSize`値パラメーターの値にします。  
  
```   
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw(); 
```  
  
### <a name="remarks"></a>コメント  
 4 番目の演算子では、単項マイナス、正負の符号を`CSize`値。 次の各演算子の説明を参照してください。  
  
- **-演算子 (** `size` **)**この操作は、2 つを減算`CSize`値。  
  
- **-演算子 (** `point` **)**この操作のオフセット (移動)、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)または[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)値これの加法に関する逆元を`CSize`値。 **Cx**と**cy**この`CSize`から値が減算されて、 **x**と**y**のデータ メンバー、**ポイント**値。 バージョンと類似している[CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-)を受け取り、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)パラメーター。  
  
- **-演算子 (** `lpRect` **)**この操作のオフセット (移動)、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)または[CRect](../../atl-mfc-shared/reference/crect-class.md)値これの加法に関する逆元を`CSize`値。 **Cx**と**cy** this のメンバー`CSize`から値が減算されて、**左**、**上部**、**右**、および**下部**のデータ メンバー、`RECT`値。 バージョンと類似している[CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-)を受け取り、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)パラメーター。  
  
- **演算子の ()**この操作はこれの加法に関する逆元を返す`CSize`値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&103;](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint クラス](../../atl-mfc-shared/reference/cpoint-class.md)


