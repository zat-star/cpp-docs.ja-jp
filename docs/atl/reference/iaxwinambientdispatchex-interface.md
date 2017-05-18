---
title: "IAxWinAmbientDispatchEx インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatchEx
- No header/ATL::IAxWinAmbientDispatchEx
- No header/ATL::SetAmbientDispatch
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 25
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
ms.openlocfilehash: 915514a021aa89b751a49a34cb53b693b9fd0c45
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx インターフェイス
このインターフェイスでは、ホストされるコントロールの補足のアンビエント プロパティを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[SetAmbientDispatch](#setambientdispatch)|このメソッドは、ユーザー定義のインターフェイスを持つ既定のアンビエント プロパティのインターフェイスを補足するために呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 ATL と ActiveX コントロール、特にアンビエント プロパティを持つ ActiveX コントロールのホストに静的にリンクされている ATL アプリケーションには、このインターフェイスを追加します。 このインターフェイスを除くと、このアサーションが生成されます:「を忘れましたかできるに LIBID を渡す」  
  
 このインターフェイスは、オブジェクトのホスト、ATL の ActiveX コントロールによって公開されます。 派生した[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)、`IAxWinAmbientDispatchEx`独自のいずれかで、ATL によって提供されるアンビエント プロパティのインターフェイスを補足するためには、メソッドを追加します。  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx)をに関する型情報を読み込んでみます`IAxWinAmbientDispatch`と`IAxWinAmbientDispatchEx`コードが含まれるタイプ ライブラリからです。  
  
 ATL90.dll にリンクしている場合は、 **AXHost**は DLL 内のタイプ ライブラリから型情報を読み込みます。  
  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)詳細です。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次の表に示すようにさまざまな形式で使用できます。  
  
|定義の種類|ファイル|  
|---------------------|----------|  
|IDL|atliface.idl|  
|タイプ ライブラリ|ATL.dll|  
|C++|atliface.h (ATLBase.h にも含まれます)|  
  
##  <a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch  
 このメソッドは、ユーザー定義のインターフェイスを持つ既定のアンビエント プロパティのインターフェイスを補足するために呼び出されます。  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 *pDispatch*  
 新しいインターフェイスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 ときに`SetAmbientDispatch`と呼ばれるプロパティまたはメソッドがこれらのプロパティが既に提供しない場合、ホストされるコントロールによるに求められる呼び出しに、この新しいインターフェイスを使用を新しいインターフェイスへのポインターで[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)します。  
  
## <a name="see-also"></a>関連項目  
 [IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)

