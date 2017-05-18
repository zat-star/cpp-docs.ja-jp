---
title: "OLE コントロールの登録 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- registering OLE controls
- OLE controls, registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
caps.latest.revision: 15
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 9c54fb7dc3802e78c8dc68df02ff55ef4732a36b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="registering-ole-controls"></a>OLE コントロールの登録
その他の OLE サーバー オブジェクトと同様に、OLE コントロールは、その他の OLE に対応するアプリケーションからアクセスできます。 これは、コントロールのタイプ ライブラリとクラスを登録することによって実現されます。  
  
 次の機能を追加および Windows registration データベースに、コントロールのクラス、プロパティ ページ、およびタイプ ライブラリを削除できます。  
  
### <a name="registering-ole-controls"></a>OLE コントロールの登録  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|コントロールのクラスを登録データベースに追加します。|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|登録情報データベースには、コントロールのプロパティ ページを追加します。|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|コントロールのタイプ ライブラリを登録データベースに追加します。|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|登録情報データベースから、コントロール クラスまたはプロパティ ページのクラスを削除します。|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|コントロールのタイプ ライブラリを登録情報データベースから削除します。|  
  
 `AfxOleRegisterTypeLib`通常の制御 DLL の実装で呼び出されます`DllRegisterServer`します。 同様に、`AfxOleUnregisterTypeLib`によって呼び出される`DllUnregisterServer`です。 `AfxOleRegisterControlClass`、 `AfxOleRegisterPropertyPageClass`、および`AfxOleUnregisterClass`通常と呼ばれる、`UpdateRegistry`コントロールのクラス ファクトリまたはプロパティ ページのメンバー関数。  
  
##  <a name="afxoleregistercontrolclass"></a>AfxOleRegisterControlClass  
 コントロール クラスを Windows の登録データベースに登録します。  
  
```   
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,  
    REFCLSID clsid,  
    LPCTSTR pszProgID,  
    UINT idTypeName,  
    UINT idBitmap,  
    int nRegFlags,  
    DWORD dwMiscStatus,  
    REFGUID tlid,  
    WORD wVerMajor,  
    WORD wVerMinor); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 コントロール クラスに関連付けられているモジュールのインスタンス ハンドル。  
  
 `clsid`  
 コントロールの一意のクラス ID。  
  
 `pszProgID`  
 コントロールの固有のプログラム ID。  
  
 `idTypeName`  
 コントロールのユーザーが判読できる形式名を含む文字列のリソース ID。  
  
 *idBitmap*  
 ツールバーまたはパレットでの OLE コントロールを表すために使用するビットマップのリソース ID です。  
  
 `nRegFlags`  
 次のフラグの&1; つ以上含まれています。  
  
- `afxRegInsertable`OLE オブジェクトのオブジェクトの挿入 ダイアログ ボックスに表示するには、制御できます。  
  
- `afxRegApartmentThreading`スレッド処理モデルを ThreadingModel をレジストリに設定 = アパートメントします。  
  
- `afxRegFreeThreading`スレッド処理モデルを ThreadingModel をレジストリに設定 = 無料です。  
  
     2 つのフラグを結合する`afxRegApartmentThreading`と`afxRegFreeThreading`ThreadingModel を設定する = Both です。 参照してください[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]スレッド モデルの登録の詳細についてです。  
  
> [!NOTE]
>  MFC 4.2 より前に、のバージョンの MFC で、 `int` `nRegFlags`パラメーターが指定されて、 **BOOL**パラメーター、 *bInsertable*、許可する、またはオブジェクトの挿入 ダイアログ ボックスから挿入されるコントロールを禁止します。  
  
 *dwMiscStatus*  
 次の状態フラグの&1; つ以上含まれています (フラグの説明は、次を参照してください。**入ります**内の列挙型、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)])。  
  
-   OLEMISC_RECOMPOSEONRESIZE  
  
-   OLEMISC_ONLYICONIC  
  
-   OLEMISC_INSERTNOTREPLACE  
  
-   OLEMISC_STATIC  
  
-   OLEMISC_CANTLINKINSIDE  
  
-   OLEMISC_CANLINKBYOLE1  
  
-   OLEMISC_ISLINKOBJECT  
  
-   OLEMISC_INSIDEOUT  
  
-   されて  
  
-   OLEMISC_RENDERINGISDEVICEINDEPENDENT  
  
-   OLEMISC_INVISIBLEATRUNTIME  
  
-   OLEMISC_ALWAYSRUN  
  
-   OLEMISC_ACTSLIKEBUTTON  
  
-   OLEMISC_ACTSLIKELABEL  
  
-   OLEMISC_NOUIACTIVATE  
  
-   OLEMISC_ALIGNABLE  
  
-   OLEMISC_IMEMODE  
  
-   OLEMISC_SIMPLEFRAME  
  
-   OLEMISC_SETCLIENTSITEFIRST  
  
 *tlid*  
 コントロール クラスの一意の ID。  
  
 `wVerMajor`  
 コントロール クラスのメジャー バージョン番号。  
  
 `wVerMinor`  
 コントロール クラスのマイナー バージョン番号。  
  
### <a name="return-value"></a>戻り値  
 コントロールのクラスが登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これにより、OLE コントロールを認識するコンテナーで使用するコントロール。 `AfxOleRegisterControlClass`コントロールの名前と、システム上の場所で、レジストリを更新しも、レジストリで、コントロールがサポートしているスレッド モデルを設定します。 詳細については、次を参照してください。[テクニカル ノート 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)、"アパートメント モデルのスレッドで OLE コントロール"は、と[に関するプロセスおよびスレッド](http://msdn.microsoft.com/library/windows/desktop/ms681917)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl&#11;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 上記の例では、どのように`AfxOleRegisterControlClass`挿入可能なフラグを使用して呼び出されたとフラグのアパートメント モデルの&6; 番目のパラメーターを作成する論理和。  
  
 [!code-cpp[NVC_MFCAxCtl&#12;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 有効なコンテナーでは、オブジェクトの挿入 ダイアログ ボックスに、コントロールが表示され、アパートメント モデルを認識がなります。 アパートメント モデルに対応したコントロールでは、1 つのアパートメントでのコントロールは、静的データにアクセスするときに、無効になっていなかったスケジューラによってが完了したら、同じ静的データを使用して、同じクラスの別のインスタンスを開始する前にできるように静的クラスのデータは、ロックで保護のことを確認する必要があります。 静的なデータへのアクセスはクリティカル セクションのコードで囲まれます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>AfxOleRegisterPropertyPageClass  
 プロパティ ページのクラスを Windows の登録データベースに登録します。  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 プロパティ ページ クラスに関連付けられているモジュールのインスタンス ハンドル。  
  
 `clsid`  
 プロパティ ページの一意のクラス ID。  
  
 `idTypeName`  
 プロパティ ページのユーザーが判読できる名前を表す文字列のリソース ID。  
  
 `nRegFlags`  
 フラグを含めることがあります。  
  
- `afxRegApartmentThreading`スレッド処理モデルを ThreadingModel をレジストリに設定 = アパートメントします。  
  
> [!NOTE]
>  MFC 4.2 は、以前のバージョンの MFC で、 `int` `nRegFlags`パラメーターは使用できませんでした。 なお、`afxRegInsertable`フラグは、プロパティ ページの有効なオプションではありませんし、によって設定されている場合、MFC で ASSERT を実行  
  
### <a name="return-value"></a>戻り値  
 コントロールのクラスが登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これにより、OLE コントロールを認識するコンテナーで使用されるプロパティ ページです。 `AfxOleRegisterPropertyPageClass`プロパティ ページの名前と、システム上の場所のレジストリを更新し、また、レジストリで、コントロールがサポートしているスレッド モデルを設定します。 詳細については、次を参照してください。[テクニカル ノート 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md)、"アパートメント モデルのスレッドで OLE コントロール"は、と[に関するプロセスおよびスレッド](http://msdn.microsoft.com/library/windows/desktop/ms681917)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>AfxOleRegisterTypeLib  
 Windows 登録データベースのタイプ ライブラリを登録し、OLE コントロールを認識している他のコンテナーで使用されるタイプ ライブラリを使用します。  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 タイプ ライブラリに関連付けられているアプリケーションのインスタンス ハンドル。  
  
 *tlid*  
 タイプ ライブラリの一意の ID。  
  
 *pszFileName*  
 ローカライズされたタイプ ライブラリの省略可能なファイル名を指す (します。コントロールの TLB) ファイルです。  
  
 *pszHelpDir*  
 タイプ ライブラリのヘルプ ファイルの場所のディレクトリの名前。 場合**NULL**、ヘルプ ファイルが、タイプ ライブラリ自体と同じディレクトリにあると見なされます。  
  
### <a name="return-value"></a>戻り値  
 タイプ ライブラリが登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、タイプ ライブラリ名と、システム上の場所のレジストリを更新します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation&#7;](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation&#8;](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>AfxOleUnregisterClass  
 Windows 登録情報データベースからのコントロールまたはプロパティ ページ クラスのエントリを削除します。  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>パラメーター  
 *clsID*  
 コントロールまたはプロパティ ページの一意のクラス ID。  
  
 `pszProgID`  
 コントロールまたはプロパティ ページの固有のプログラム ID。  
  
### <a name="return-value"></a>戻り値  
 コントロールまたはプロパティ ページ クラスが正常に登録できなかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>AfxOleUnregisterTypeLib  
 Windows 登録情報データベースからタイプ ライブラリのエントリを削除するには、この関数を呼び出します。  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>パラメーター  
 `tlID`  
 タイプ ライブラリの一意の ID。  
  
### <a name="return-value"></a>戻り値  
 タイプ ライブラリが正常に登録できなかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAxCtl&#13;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

