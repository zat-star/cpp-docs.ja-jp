---
title: "クラス ファクトリとライセンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- class factories, and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: a8ef7ba19d2337e4e50f34d7cdd528024a1d90aa
ms.lasthandoff: 02/24/2017

---
# <a name="class-factories-and-licensing"></a>クラス ファクトリとライセンス
OLE コントロールのインスタンスを作成するには、コンテナー アプリケーションは、コントロールのクラス ファクトリのメンバー関数を呼び出します。 コントロールは、実際の OLE オブジェクトであるため、クラス ファクトリは、コントロールのインスタンスを作成します。 すべての OLE コントロール クラスには、クラス ファクトリが必要です。  
  
 OLE コントロールのもう&1; つの重要な機能では、ライセンスを強制できる点です。 ControlWizard を使用すると、コントロール プロジェクトの作成時にライセンスを組み込むことができます。 コントロールのライセンスの詳細については、記事を参照して[ActiveX コントロール: ActiveX コントロールの ライセンス](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)。  
  
 次の表は、いくつかのマクロと関数を宣言し、コントロールのクラス ファクトリを実装するために使用し、コントロールのライセンスを取得します。  
  
### <a name="class-factories-and-licensing"></a>クラス ファクトリとライセンス  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE コントロールまたはプロパティ ページのクラス ファクトリを宣言します。|  
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|コントロールの実装`GetClassID`関数し、クラス ファクトリのインスタンスが宣言されています。|  
|[BEGIN_OLEFACTORY](#begin_olefactory)|ライセンス関数の宣言を開始します。|  
|[END_OLEFACTORY](#end_olefactory)|ライセンス関数の宣言を終了します。|  
|[AfxVerifyLicFile](#afxverifylicfile)|コントロールが特定のコンピューターで使用するためにライセンスされているかどうかを確認します。|  
  
##  <a name="a-namedeclareolecreateexa--declareolecreateex"></a><a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX  
 クラス ファクトリを宣言し、`GetClassID`コントロール クラスのメンバー関数。  
  
```   
DECLARE_OLECREATE_EX(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 コントロール クラスの名前。  
  
### <a name="remarks"></a>コメント  
 ライセンスをサポートしない、コントロールのコントロール クラスのヘッダー ファイルには、このマクロを使用します。  
  
 このマクロは、次のコード サンプルと同じ目的に注意してください。  
  
 [!code-cpp[NVC_MFCAxCtl&#14;](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameimplementolecreateexa--implementolecreateex"></a><a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX  
 コントロールのクラス ファクトリを実装し、 [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid)コントロール クラスのメンバー関数。  
  
```   
IMPLEMENT_OLECREATE_EX(
   class_name,   
    external_name,    
    l,   
    w1,   
    w2,   
    b1,   
    b2,   
    b3,   
    b4,   
    b5,   
    b6,   
    b7,
    b8)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 コントロールのプロパティ ページ クラスの名前。  
  
 *external_name*  
 アプリケーションに公開されるオブジェクトの名前。  
  
 *l、w1、w2、b1、b2、b3、b4、b5、b6、b7、b8*  
 クラスのコンポーネント**CLSID**します。 これらのパラメーターの詳細については、「解説」を参照してください。 [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate)します。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するコントロール クラスの実装ファイルに表示する必要があります、`DECLARE_OLECREATE_EX`マクロまたは`BEGIN_OLEFACTORY`と`END_OLEFACTORY`マクロです。 外部の名前は、他のアプリケーションに公開されている OLE コントロールの識別子です。 コンテナーでは、この名前を使用して、このコントロール クラスのオブジェクトを要求します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-namebeginolefactorya--beginolefactory"></a><a name="begin_olefactory"></a>BEGIN_OLEFACTORY  
 コントロール クラスのヘッダー ファイルで、クラス ファクトリの宣言を開始します。  
  
``` 
BEGIN_OLEFACTORY(class_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 これは、クラス ファクトリを持つコントロール クラスの名前を指定します。  
  
### <a name="remarks"></a>コメント  
 クラス ファクトリ ライセンス関数の宣言の直後に開始`BEGIN_OLEFACTORY`します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameendolefactorya--endolefactory"></a><a name="end_olefactory"></a>END_OLEFACTORY  
 コントロールのクラス ファクトリの宣言を終了します。  
  
```  
END_OLEFACTORY(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 これは、クラス ファクトリを持つコントロール クラスの名前。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="a-nameafxverifylicfilea--afxverifylicfile"></a><a name="afxverifylicfile"></a>AfxVerifyLicFile  
 ライセンス ファイルが付けたことを確認するには、この関数を呼び出す`pszLicFileName`は OLE コントロールに対して有効です。  
  
```   
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,  
    LPCTSTR  pszLicFileName,  
    LPOLESTR  pszLicFileContents,  
    UINT cch = -1); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 ライセンスされたコントロールに関連付けられている DLL のインスタンス ハンドル。  
  
 `pszLicFileName`  
 ライセンス ファイル名を含む null で終わる文字列へのポインター。  
  
 `pszLicFileContents`  
 ライセンス ファイルの先頭にあるシーケンスと一致するバイト シーケンスを指します。  
  
 `cch`  
 内の文字数`pszLicFileContents`します。  
  
### <a name="return-value"></a>戻り値  
 ライセンス ファイルが存在しの文字の組み合わせで始まる場合は 0 以外`pszLicFileContents`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 場合`cch`â € は、"1、この関数を使用します。  
  
 [!code-cpp[NVC_MFC_Utilities&#36;](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]  

### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

