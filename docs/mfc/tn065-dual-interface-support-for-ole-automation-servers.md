---
title: "テクニカル ノート 65: OLE オートメーション サーバー用デュアル インターフェイス サポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACDUAL サンプル [MFC]"
  - "オートメーション サーバー, デュアル インターフェイスのサポート"
  - "デュアル インターフェイス, OLE オートメーション"
  - "TN065"
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# テクニカル ノート 65: OLE オートメーション サーバー用デュアル インターフェイス サポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは、MFC ベースの OLE オートメーション サーバーのアプリケーションにデュアル インターフェイス サポートを追加する方法について説明します。  [ACDUAL](../top/visual-cpp-samples.md) サンプルは、デュアル インターフェイス サポートを示し、ここでのコード例は、ACDual から取得されます。  ここでは、`DECLARE_DUAL_ERRORINFO`など、`DUAL_ERRORINFO_PART`説明されているマクロと `IMPLEMENT_DUAL_ERRORINFO`、ACDual サンプルの一部であり、MFCDUAL.H.で確認できます。  
  
## デュアル インターフェイス  
 OLE オートメーションが実装することを両方の包含\) `IDispatch` インターフェイス、VTBL インターフェイスをデュアル インターフェイス \(できますが、Microsoft は厳密に公開されているすべての OLE オートメーション オブジェクトのデュアル インターフェイスを実装することをお勧めします。  デュアル インターフェイスに `IDispatch`のみまたは VTBL インターフェイスのみより大きな利点があります:  
  
-   バインドは `IDispatch`で VTBL インターフェイスを通じて、コンパイル時または実行時に発生することがあります。  
  
-   VTBL インターフェイスを使用して、OLE オートメーションのコントローラーはパフォーマンスの向上の余地があります。  
  
-   `IDispatch` インターフェイスを使用する既存の OLE オートメーションのコントローラーは引き続き機能します。  
  
-   VTBL インターフェイスは C\+\+ から呼び出すより簡単です。  
  
-   Visual Basic のオブジェクトが機能を持つデュアル インターフェイスは互換性のために必要です。  
  
## CCmdTarget ベースのクラスにデュアル インターフェイス サポートを追加できます。  
 デュアル インターフェイスは `IDispatch`から派生される実際に、カスタム インターフェイスです。  `CCmdTarget`のベースのクラスにデュアル インターフェイス サポートを実装する最も簡単な方法は、MFC クラス ウィザードを使用するには、最初に実装しましたりクラスの正常なディスパッチ インターフェイスを、後で追加するカスタム インターフェイスを持ちます。  ほとんどの場合、カスタム インターフェイスの実装は、MFC `IDispatch` の実装が単に委任します。  
  
 最初に、オブジェクトのデュアル インターフェイスを定義するサーバーの ODL ファイルを変更します。  デュアル インターフェイスを定義するには、Visual C\+\+ ウィザードが生成する `DISPINTERFACE` のステートメントの代わりにインターフェイス ステートメントを使用する必要があります。  `DISPINTERFACE` の既存のステートメントを削除するのではなく、新しいインターフェイス ステートメントを追加します。  `DISPINTERFACE` のフォームを保持すると、オブジェクトがプロパティとメソッドの追加に ClassWizard を使用し続けることができます Interface ステートメントと同等のプロパティおよびメソッドを追加する必要があります。  
  
 デュアル インターフェイスのインターフェイス ステートメントは **OLEAUTOMATION** と **DUAL** 属性を持つインターフェイスは `IDispatch`から派生されなければなりません。  デュアル インターフェイスの **IID** の作成に [GUIDGEN](../top/visual-cpp-samples.md) のサンプルを使用する場合:  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
   oleautomation,  
   dual  
]  
interface IDualAClick : IDispatch  
  {  
  };  
```  
  
 適切なインターフェイスのステートメントがある場合は、メソッドやプロパティのエントリの追加を開始します。  デュアル インターフェイスでは、デュアル インターフェイスのメソッドとプロパティ アクセサー関数が `HRESULT` を返し、`[retval,out]`属性のパラメーターとして戻り値を返すようにパラメーター リストを並べ替える必要があります。  プロパティに対して、Read \(`propget`\) 追加し \(同じ ID を持つ`propput`\) アクセス関数を記述する必要があることに注意してください。  たとえば、次のようになります。  
  
```  
[propput, id(1)] HRESULT text([in] BSTR newText);  
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);  
```  
  
 メソッドとプロパティの後、Interface ステートメントへの参照を追加する必要がありますコクラスのステートメントで定義されます。  たとえば、次のようになります。  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
   dispinterface IAClick;  
   [default] interface IDualAClick;  
};  
```  
  
 ODL ファイルが更新されたら、Object クラスのデュアル インターフェイスを実装するクラスを定義し、MFC の `QueryInterface` 機能の対応するエントリを行うために MFC のインターフェイス マップ機構を使用します。  ディスパッチ インターフェイスのエントリが ODL の Interface ステートメントの各エントリの `INTERFACE_PART` ブロックで 1 エントリが必要です。  **propput** 属性の各エントリは `put_propertyname`ODL という名前の関数が必要です。  **propget** 属性の各エントリは `get_propertyname`という名前の関数が必要です。  
  
 デュアル インターフェイスを実装するクラスを定義するには、オブジェクトのクラス定義に `DUAL_INTERFACE_PART` ブロックを追加します。  たとえば、次のようになります。  
  
```  
BEGIN_DUAL_INTERFACE_PART(DualAClick, IDualAClick)  
  STDMETHOD(put_text)(THIS_ BSTR newText);  
  STDMETHOD(get_text)(THIS_ BSTR FAR* retval);  
  STDMETHOD(put_x)(THIS_ short newX);  
  STDMETHOD(get_x)(THIS_ short FAR* retval);  
  STDMETHOD(put_y)(THIS_ short newY);  
  STDMETHOD(get_y)(THIS_ short FAR* retval);  
  STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);  
  STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);  
  STDMETHOD(RefreshWindow)(THIS);  
  STDMETHOD(SetAllProps)(THIS_ short x, short y, BSTR text);  
  STDMETHOD(ShowWindow)(THIS);  
END_DUAL_INTERFACE_PART(DualAClick)  
```  
  
 MFC の [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) の機能にデュアル インターフェイスを接続するには、`INTERFACE_PART` インターフェイス マップにエントリを追加する:  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)  
  INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)  
  INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)  
END_INTERFACE_MAP()  
```  
  
 次に、インターフェイスの実装を設定する必要があります。  ほとんどの場合、既存の MFC `IDispatch` の実装に委任できます。  たとえば、次のようになります。  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   return pThis->ExternalAddRef();  
}  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   return pThis->ExternalRelease();  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(  
             REFIID iid, LPVOID* ppvObj)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   return pThis->ExternalQueryInterface(&iid, ppvObj);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(  
            UINT FAR* pctinfo)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetTypeInfoCount(pctinfo);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(  
          UINT itinfo, LCID lcid, ITypeInfo FAR* FAR* pptinfo)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetTypeInfo(itinfo, lcid, pptinfo);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(  
       REFIID riid, OLECHAR FAR* FAR* rgszNames, UINT cNames,  
       LCID lcid, DISPID FAR* rgdispid)   
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetIDsOfNames(riid, rgszNames, cNames,   
                                    lcid, rgdispid);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(  
    DISPID dispidMember, REFIID riid, LCID lcid, WORD wFlags,  
    DISPPARAMS FAR* pdispparams, VARIANT FAR* pvarResult,  
    EXCEPINFO FAR* pexcepinfo, UINT FAR* puArgErr)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->Invoke(dispidMember, riid, lcid,  
                             wFlags, pdispparams, pvarResult,  
                             pexcepinfo, puArgErr);  
}  
```  
  
 オブジェクトのメソッドとプロパティ アクセサー関数の場合は、実装を設定する必要があります。  メソッドとプロパティは、ClassWizard 関数を使用して生成されたメソッドに対して一般的に委任できます。  ただし、変数に直接アクセスするためのプロパティを設定し、取得するコードを記述する必要があります。\/変数の値を取得します。  たとえば、次のようになります。  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   // MFC automatically converts from Unicode BSTR to   
   // Ansi CString, if necessary...  
   pThis->m_str = newText;  
   return NOERROR;  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   // MFC automatically converts from Ansi CString to   
   // Unicode BSTR, if necessary...  
   pThis->m_str.SetSysString(retval);  
   return NOERROR;  
}  
```  
  
## デュアル インターフェイス ポインターを渡します。  
 デュアル インターフェイス ポインターを渡すと、特に `CCmdTarget::FromIDispatch`を呼び出すときは、簡単ではありません。  `FromIDispatch` は MFC の `IDispatch` ポインターでのみ動作します。  これに対処する 1 番目の方法は、MFC によって元の `IDispatch` ポインターのセットアップを呼び出し、それを必要とする関数にポインターを渡すことです。  たとえば、次のようになります。  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_Position(  
      IDualAutoClickPoint FAR* newPosition)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDisp = NULL;  
   newPosition->QueryInterface(IID_IDispatch, (LPVOID*)&lpDisp);  
   pThis->SetPosition(lpDisp);  
   lpDisp->Release();  
   return NOERROR;  
}  
```  
  
 デュアル インターフェイスのメソッドは、ポインターを渡す前に、MFC `IDispatch` のポインターのデュアル インターフェイス ポインターに変換する必要がある場合があります。  たとえば、次のようになります。  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_Position(  
      IDualAutoClickPoint FAR* FAR* retval)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDisp;  
   lpDisp = pThis->GetPosition();  
   lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);  
   return NOERROR;  
}  
```  
  
## アプリケーションのタイプ ライブラリの登録  
 AppWizard はシステムへの OLE オートメーション サーバー アプリケーションのタイプ ライブラリを登録するためのコードを生成しません。  タイプ ライブラリを登録するもう一つの方法では、アプリケーションが実行されたスタンドアロンになるたびに、OLE 型情報を、つまり更新しているときにアプリケーション レジスタを持つタイプ ライブラリと便利です。  
  
 アプリケーションが実行されるスタンドアロンのである場合、アプリケーションのタイプ ライブラリを登録するには:  
  
-   標準に AFXCTL.H を `AfxOleRegisterTypeLib` 関数の定義にアクセスするために含まれているヘッダー ファイル、STDAFX.H、を含めます。  
  
-   アプリケーションの `InitInstance` 関数では、`COleObjectFactory::UpdateRegistryAll`に呼び出しを探します。  この呼び出しの後で、タイプ ライブラリの名前とともにタイプ ライブラリに対応する **LIBID** を指定する `AfxOleRegisterTypeLib`への呼び出しを追加する:  
  
    ```  
    // When a server application is launched stand-alone, it is a good idea  
    // to update the system registry in case it has been damaged.  
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);  
    COleObjectFactory::UpdateRegistryAll();  
    // DUAL_SUPPORT_START  
    // Make sure the type library is registered or dual interface won't work.  
    AfxOleRegisterTypeLib(AfxGetInstanceHandle(), LIBID_ACDual, _T("AutoClik.TLB"));  
    // DUAL_SUPPORT_END  
    ```  
  
## タイプ ライブラリの変更を受け入れる Project Build の設定の変更  
 タイプ ライブラリを再度ビルドするたびにヘッダーのファイルの **UUID** 定義が MkTypLib によって生成されるように、プロジェクトのビルド構成を変更するには:  
  
1.  **\[ビルド\]** メニューで、**\[設定\]** をクリックします、各構成にファイル リストから ODL ファイルを選択します。  
  
2.  **OLE Types** タブをクリックし、**出力ヘッダー** のファイル名フィールドにファイル名を指定します。  MkTypLib が既存のファイルが上書きされるため、プロジェクトで既に使用されていないファイル名を使用します。  **ビルド設定** ダイアログ ボックスを閉じるに **\[OK\]** をクリックします。  
  
 **UUID** 定義を MkTypLib 生成されるヘッダー ファイルからプロジェクトに追加するには:  
  
1.  標準に MkTypLib 生成されるヘッダー ファイルを含むヘッダー ファイル、STDAFX.H.を含めます。  
  
2.  新しいファイル、INITIIDS.CPP を作成し、プロジェクトに追加します。  このファイルでは、OLE2.H と INITGUID.H を含む MkTypLib 生成されるヘッダー ファイルをインクルードする:後  
  
    ```  
    // initIIDs.c: defines IIDs for dual interfaces  
    // This must not be built with precompiled header.  
      #include <ole2.h>  
      #include <initguid.h>  
      #include "acdual.h"  
    ```  
  
3.  **\[ビルド\]** メニューで、**\[設定\]** をクリックします、各構成ファイルに INITIIDS.CPP を一覧から選択します。  
  
4.  **C\+\+** タブをクリックし、**プリコンパイル済みヘッダー**カテゴリをクリックして、**プリコンパイル済みヘッダーを使用しない** のオプション ボタンを選択します。  **ビルド設定** ダイアログ ボックスを閉じる場合は OK をクリックします。  
  
## タイプ ライブラリ内の正しいオブジェクト クラス名を指定できます。  
 ウィザードは、OLE できないクラスに Visual C\+\+ で不正に使用するサーバーの ODL ファイルでコクラスを指定するには、実装クラス名を提供します。  これはありませんが、実装クラス名は、開発に使用するオブジェクトのユーザーが必要とするクラス名ではありません。  正しい名前を指定するには、ODL ファイルを開き、各コクラスのステートメントを探し、正しい外部名と実装クラス名を置き換えます。  
  
 コクラスのステートメントが変更されると、MkTypLib 生成されるヘッダー ファイルの **CLSID**s の変数名はそれに応じて変更されることに注意してください。  新しい変数名を使用するようにコードを更新する必要があります。  
  
## 例外処理とオートメーション エラー インターフェイス  
 オートメーション オブジェクトのメソッドとプロパティ アクセサー関数が例外をスローすることがあります。  その場合、**IErrorInfo**をデュアル インターフェイスの実装で処理し、コントローラーが OLE オートメーションのエラー処理インターフェイスを通じて例外に関する情報を渡します。  このインターフェイスは `IDispatch` と VTBL インターフェイスの両方を使用して、詳細なコンテキスト キーワードのエラー情報を提供します。  エラー ハンドラーが使用できることを示すには、**ISupportErrorInfo\(I\)** インターフェイスを実装する必要があります。  
  
 例外処理機構を説明するには、標準ディスパッチ サポート throw 例外を実装するために使用される ClassWizard 生成された関数とします。  MFC の **IDispatch::Invoke** の実装は、通常、これらの例外をキャッチして `Invoke` の呼び出しによって返される EXCEPTINFO 構造体に変換します。  ただし、VTBL インターフェイスを使用すると、例外をキャッチすることを独自に管理します。  デュアル インターフェイスのメソッドを保護する例として:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   TRY_DUAL(IID_IDualAClick)  
   {  
      // MFC automatically converts from Unicode BSTR to   
      // Ansi CString, if necessary...  
      pThis->m_str = newText;  
      return NOERROR;  
   }  
   CATCH_ALL_DUAL  
}  
```  
  
 `CATCH_ALL_DUAL` は 例外が発生すると、エラー コードを返します。処理します。  `CATCH_ALL_DUAL` は **ICreateErrorInfo** インターフェイスを使用して OLE オートメーションのエラー処理情報に MFC 例外を変換します。\(この例では `CATCH_ALL_DUAL` マクロは [ACDUAL](../top/visual-cpp-samples.md) サンプルのファイル MFCDUAL.H にあります。  その例外処理に呼び出す関数 `DualHandleException`は、発生した例外の種類によっては、ファイル MFCDUAL.CPP\)。`CATCH_ALL_DUAL`、をエラー コードがあります:  
  
-   この場合[COleDispatchException](../Topic/COleDispatchException%20Class.md) –は次のコードを使用して、`HRESULT` 生成:  
  
    ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF,   
                               (e->m_wCode + 0x200));  
    ```  
  
     これは、例外の原因となったインターフェイスに `HRESULT` 仕様を作成します。  エラー コードは 0x200 自体によって標準 OLE インターフェイスのシステム定義の `HRESULT`s の競合を避けるために、オフセットされます。  
  
-   この場合[CMemoryException](../mfc/reference/cmemoryexception-class.md) –は、`E_OUTOFMEMORY` 返されます。  
  
-   この場合、他の–、`E_UNEXPECTED` 例外が返されます。  
  
 OLE オートメーションのエラー ハンドラーが使用されることを示すには、**ISupportErrorInfo\(I\)** インターフェイスを実装する必要があります。  
  
 最初に **ISupportErrorInfo\(I\)**をサポートする必要があることを示すために、オートメーション クラス定義にコードを追加します。  
  
 第 2 に、MFC の `QueryInterface` の機能によって **ISupportErrorInfo\(I\)** の実装クラスを関連付けるには、オートメーション クラスのインターフェイス マップにコードを追加します。  `INTERFACE_PART` のステートメントは **ISupportErrorInfo\(I\)**に定義されているクラスを検索します。  
  
 最後に、**ISupportErrorInfo\(I\)**をサポートするために定義されているクラスを実装してください。  
  
 \([ACDUAL](../top/visual-cpp-samples.md) サンプルはするための 3 種類のマクロを行います。この手順 3、`DECLARE_DUAL_ERRORINFO`、完全に MFCDUAL.H.に含まれる `DUAL_ERRORINFO_PART`と `IMPLEMENT_DUAL_ERRORINFO`が含まれます\)  
  
 次の例では **ISupportErrorInfo\(I\)**をサポートするために定義されているクラスを実装します。  `CAutoClickDoc` は オートメーション クラスの名前であり、`IID_IDualAClick` は OLE オートメーションの Error オブジェクトで報告される間違いのソース インターフェイスの **IID** です:  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::AddRef()   
{  
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return pThis->ExternalAddRef();   
}   
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::Release()   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return pThis->ExternalRelease();   
}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface(   
   REFIID iid, LPVOID* ppvObj)   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return pThis->ExternalQueryInterface(&iid, ppvObj);   
}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo(   
   REFIID iid)   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return (iid == IID_IDualAClick) ? S_OK : S_FALSE;   
}  
```  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)