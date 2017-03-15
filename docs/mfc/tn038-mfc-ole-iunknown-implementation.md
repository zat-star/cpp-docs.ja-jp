---
title: "テクニカル ノート 38: MFC/OLE IUnknown の実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "集約マクロ [C++]"
  - "BEGIN_INTERFACE_MAP マクロ"
  - "BEGIN_INTERFACE_PART マクロ"
  - "COM インターフェイス, 基本インターフェイス"
  - "DECLARE_INTERFACE_MAP マクロ"
  - "END_INTERFACE_MAP マクロ"
  - "END_INTERFACE_PART マクロ"
  - "INTERFACE_PART マクロ"
  - "IUnknown インターフェイス"
  - "METHOD_PROLOGUE マクロ"
  - "OLE [C++], 実装 (IUnknown インターフェイスを)"
  - "STDMETHOD マクロ"
  - "TN038"
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# テクニカル ノート 38: MFC/OLE IUnknown の実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 OLE 2 の中核は、"OLE コンポーネント オブジェクト モデル \(COM: Component Object Model\)" です。  COM は、複数のオブジェクトが相互に協調して通信するための基準を定義しています。  この定義には、オブジェクトにメソッドをディスパッチする方法など、"オブジェクト" を外から見たときの詳細が含まれています。  COM にはまた、基底クラスが定義されています。COM 対応のクラスはすべてこのクラスから派生します。  この基底クラスは [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) というクラスです。  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) インターフェイスは C\+\+ クラスと呼ばれていますが、COM の利用は特定の言語に限定されていません。C や PASCAL など、COM オブジェクトのバイナリ形式をサポートするすべての言語で COM を実装できます。  
  
 OLE では、すべての [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 派生クラスを "インターフェイス" と呼びます。 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) などの "インターフェイス" と呼ばれるクラスは実装を持ちません。このことは重要な違いです。  この "インターフェイス" と呼ばれるクラスは、オブジェクト間の通信プロトコルだけを定義し、その具体的な実装は定義していません。  これは、システムの最大限の柔軟性を確保するためです。  MFC\/C\+\+ プログラムの既定の動作は、MFC \(Microsoft Foundation Class\) によって実装されます。  
  
 MFC による [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) の実装を理解するには、その前にまず、このインターフェイスについて理解する必要があります。  簡単な [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) の定義を次に示します。  
  
```  
class IUnknown  
{  
public:  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;  
    virtual ULONG AddRef() = 0;  
    virtual ULONG Release() = 0;  
};  
```  
  
> [!NOTE]
>  この説明では、必要な呼び出し規約の詳細の一部 \(`__stdcall` など\) を省略しています。  
  
 メンバー関数、[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) および [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) は、オブジェクトのメモリ管理を制御します。  COM は、参照カウント スキームを使用してオブジェクトを追跡します。  C\+\+ と異なり、オブジェクトが直接参照されることはありません。  COM オブジェクトは、常にポインターを通じて参照されます。  オブジェクトが不要になると、所有者はオブジェクトの [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) メンバーを呼び出して不要なオブジェクトを解放します \(従来の C\+\+ オブジェクトのような delete 演算子は使用しません\)。  参照カウント スキームを使用することで、単一オブジェクトに対する多重参照を管理できます。  オブジェクトの参照カウントは、[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) と [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) の実装によって管理されます。オブジェクトは、参照カウントが 0 になるまで削除されません。  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) と [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) の実装はきわめて単純です。  実装では次の処理を行うだけです。  
  
```  
ULONG CMyObj::AddRef()   
{   
    return ++m_dwRef;   
}  
  
ULONG CMyObj::Release()   
{   
    if (--m_dwRef == 0)   
    {  
        delete this;   
        return 0;  
    }  
    return m_dwRef;  
}  
```  
  
 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) メンバー関数は、より高度な手法を使用しています。  メンバー関数として [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) と [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) しか持たないオブジェクトの動作は限られているので、[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) よりも多くの機能を持つオブジェクトを作成する方が実際的です。  そこで役立つのが [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) です。  QueryInterface を使用すると、1 つのオブジェクトが複数の "インターフェイス" を持つことができます。  通常、これらのインターフェイスは [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 派生クラスとして作成します。新しい機能は、このクラスの新しいメンバー関数として追加します。  COM インターフェイスでは、インターフェイス内でメンバー変数を宣言せず、メンバー関数はすべて純粋仮想として宣言します。  次に例を示します。  
  
```  
class IPrintInterface : public IUnknown  
{  
public:  
    virtual void PrintObject() = 0;  
};  
```  
  
 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) しかない場合に IPrintInterface を取得するには、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) を呼び出して `IID`IPrintInterface の  **を使用します。** `IID` は、インターフェイスを一意に識別する 128 ビットの数値です。  各インターフェイスには、開発者や OLE によって定義された `IID` があります。  `pUnk` が [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) オブジェクトへのポインターである場合、IPrintInterface を取得するためのコードは次のようになります。  
  
```  
IPrintInterface* pPrint = NULL;  
if (pUnk->QueryInterface(IID_IPrintInterface,   
    (void**)&pPrint) == NOERROR)  
{  
    pPrint->PrintObject();  
    pPrint->Release();     
        // release pointer obtained via QueryInterface  
}  
```  
  
 このように、IPrintInterface はきわめて簡単に取得できます。しかし、IPrintInterface と [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 両方のインターフェイスをサポートするオブジェクトを実装する方法が不明です。  上の例では IPrintInterface が [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) の直接派生クラスであるため、この実装は簡単です。IPrintInterface を実装すると、[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) が自動的にサポートされます。  例:  
  
```  
class CPrintObj : public CPrintInterface  
{  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);  
    virtual ULONG AddRef();  
    virtual ULONG Release();  
    virtual void PrintObject();  
};  
```  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) と [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) の実装は、前の実装例とまったく同じです。  **CPrintObj::QueryInterface** は次のようになります。  
  
```  
HRESULT CPrintObj::QueryInterface(REFIID iid, void FAR* FAR* ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
    {  
        *ppvObj = this;  
        AddRef();  
        return NOERROR;  
    }  
    return E_NOINTERFACE;  
}  
```  
  
 上のコード例に示すように、インターフェイス ID \(IID\) が認識された場合はポインターがオブジェクトに返され、認識されない場合はエラーが発生します。  また、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) の処理が成功した場合は、[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) が暗黙的に呼び出されます。  もちろん、CEditObj::Print も実装する必要があります。  上の例の場合は IPrintInterface が [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) インターフェイスから直接派生しているため、CEditObj::Print の実装は簡単です。  ただし、2 つの異なる [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 派生インターフェイスをサポートする場合は、次の作業を検討する必要があります。  
  
```  
class IEditInterface : public IUnkown  
{  
public:  
    virtual void EditObject() = 0;  
};  
```  
  
 IEditInterface と IPrintInterface の両方をサポートするクラスは、C\+\+ の多重継承を利用する方法も含めて、さまざまな方法で実装できますが、ここではクラスの入れ子を利用する方法を説明します。  
  
```  
class CEditPrintObj  
{  
public:  
    CEditPrintObj();  
  
    HRESULT QueryInterface(REFIID iid, void**);  
    ULONG AddRef();  
    ULONG Release();  
    DWORD m_dwRef;  
  
    class CPrintObj : public IPrintInterface  
    {  
    public:  
        CEditPrintObj* m_pParent;  
        virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);  
        virtual ULONG AddRef();  
        virtual ULONG Release();  
    } m_printObj;  
  
    class CEditObj : public IEditInterface  
    {  
    public:  
        CEditPrintObj* m_pParent;  
        virtual ULONG QueryInterface(REFIID iid, void** ppvObj);  
        virtual ULONG AddRef();  
        virtual ULONG Release();  
    } m_editObj;  
};  
```  
  
 以下では、上記の実装全体が含まれています。  
  
```  
CEditPrintObj::CEditPrintObj()  
{  
    m_editObj.m_pParent = this;  
    m_printObj.m_pParent = this;  
}  
  
ULONG CEditPrintObj::AddRef()   
{   
    return ++m_dwRef;  
}  
  
CEditPrintObj::Release()  
{  
    if (--m_dwRef == 0)  
    {  
        delete this;  
        return 0;  
    }  
    return m_dwRef;  
}  
  
HRESULT CEditPrintObj::QueryInterface(REFIID iid, void** ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
    {  
        *ppvObj = &m_printObj;  
        AddRef();  
        return NOERROR;  
    }  
    else if (iid == IID_IEditInterface)  
    {  
        *ppvObj = &m_editObj;  
        AddRef();  
        return NOERROR;  
    }  
    return E_NOINTERFACE;  
}  
  
ULONG CEditPrintObj::CEditObj::AddRef()   
{   
    return m_pParent->AddRef();   
}  
  
ULONG CEditPrintObj::CEditObj::Release()   
{   
    return m_pParent->Release();   
}  
  
HRESULT CEditPrintObj::CEditObj::QueryInterface(  
    REFIID iid, void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid, ppvObj);   
}  
  
ULONG CEditPrintObj::CPrintObj::AddRef()   
{   
    return m_pParent->AddRef();   
}  
  
ULONG CEditPrintObj::CPrintObj::Release()   
{   
    return m_pParent->Release();   
}  
  
HRESULT CEditPrintObj::CPrintObj::QueryInterface(  
    REFIID iid, void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid, ppvObj);   
}  
```  
  
 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) の実装の大部分は、CEditPrintObj::CEditObj と CEditPrintObj::CPrintObj に重複してコードを記述するのではなく、CEditPrintObj クラスに記述します。  これにより、コードのサイズが圧縮され、バグを回避できます。  ここで重要なのは、IUnknown インターフェイスから [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) を呼び出すことによって、オブジェクトがサポートするすべてのインターフェイスを取得できる点と、このように取得した各インターフェイスからも同じようにインターフェイスを取得できる点です。  つまり、どのインターフェイスから呼び出された場合でも、関数 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) は同じ動作を行う必要があります。  これらの埋め込みオブジェクトから "外側のオブジェクト" の実装を呼び出すために、バック ポインター \(m\_pParent\) が使用されています。  m\_pParent ポインターは CEditPrintObj コンストラクターで初期化されます。  CEditPrintObj::CPrintObj::PrintObject と CEditPrintObj::CEditObj::EditObject も同様に実装します。  オブジェクトの編集というたった 1 つの機能を追加するために、大きなコードを追加しました。  しかしインターフェイス内にメンバー関数が 1 つだけということはほとんどなく、この例の場合も、EditObject と PrintObject を 1 つのインターフェイスにまとめるのが普通です。  
  
 このように単純なシナリオを実現するために、詳細な説明と大きなコードが必要です。  しかし、MFC\/OLE クラスという代替方法を使用することで、同じ機能を簡単に実現できます。  MFC 実装では、Windows メッセージのラップに使用されるメッセージ マップに似た方法を使用します。  この機能は、*インターフェイス マップ*と呼ばれています。次では、この機能について説明します。  
  
## MFC インターフェイス マップ  
 MFC\/OLE には "インターフェイス マップ" の実装が含まれています。この実装は概念や実行方法が、MFC の "メッセージ マップ" や "ディスパッチ マップ" に似ています。  MFC インターフェイス マップには、次の基本機能があります。  
  
-   [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) クラスに組み込まれた `CCmdTarget` の標準実装。  
  
-   参照カウントの管理、および [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) と [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) による変更  
  
-   [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) のデータ駆動機構  
  
 また、インターフェイス マップは、次の拡張機能もサポートしています。  
  
-   集約可能な COM オブジェクトの作成機能  
  
-   COM オブジェクトの実装に他の集約オブジェクトを使用する機能  
  
-   これらの実装のフックや拡張  
  
 集約の詳細については、[集約](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx)に関するトピックを参照してください。  
  
 MFC インターフェイス マップの基点は `CCmdTarget` クラスです。  `CCmdTarget` クラスには、参照カウントと *IUnknown* の実装に関連するすべてのメンバー関数があります \(参照カウントの例は [にあります\)](http://msdn.microsoft.com/library/windows/desktop/ms680509) `CCmdTarget`。  OLE COM をサポートするクラスを作成するには `CCmdTarget` の派生クラスを作成し、マクロや `CCmdTarget` メンバー関数を利用して必要なインターフェイスを実装します。  MFC 実装では、上の例で示したように各インターフェイスの実装で入れ子になったクラスが使用され、  IUnknown の標準実装によって簡略化されています。また、コード簡略化のために多くのマクロも用意されています。  
  
## インターフェイス マップの基本  
  
#### MFC インターフェイス マップを利用したクラスを作成するには  
  
1.  `CCmdTarget` クラスの直接派生クラスまたは間接派生クラスを作成します。  
  
2.  派生クラスで関数 `DECLARE_INTERFACE_MAP` を定義します。  
  
3.  サポートする各インターフェイスに対して、クラス定義でマクロ `BEGIN_INTERFACE_PART` とマクロ `END_INTERFACE_PART` を使用します。  
  
4.  実装ファイルの中で、マクロ `BEGIN_INTERFACE_MAP` と `END_INTERFACE_MAP` を使用してクラスのインターフェイス マップを定義します。  
  
5.  マクロ `INTERFACE_PART` とマクロ `BEGIN_INTERFACE_MAP` の間に、サポートする各 IID に対するマクロ `END_INTERFACE_MAP` を記述します。これによって、IID とそのクラスの中の特定の "部分" が対応付けられます。  
  
6.  入れ子になったクラスとして、サポートするインターフェイスを実装します。  
  
7.  親 \(`METHOD_PROLOGUE` 派生オブジェクト\) にアクセスするにはマクロ `CCmdTarget` を使用します。  
  
8.  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) の代わりに、これらの関数の `CCmdTarget` 実装である `ExternalAddRef`、`ExternalRelease`、`ExternalQueryInterface` を使用できます。  
  
 上の例の CPrintEditObj の場合は次のように実装できます。  
  
```  
class CPrintEditObj : public CCmdTarget  
{  
public:  
    // member data and member functions for CPrintEditObj go here  
  
// Interface Maps  
protected:  
    DECLARE_INTERFACE_MAP()  
  
    BEGIN_INTERFACE_PART(EditObj, IEditInterface)  
        STDMETHOD_(void, EditObject)();  
    END_INTERFACE_PART(EditObj)  
  
    BEGIN_INTERFACE_PART(PrintObj, IPrintInterface)  
        STDMETHOD_(void, PrintObject)();  
    END_INTERFACE_PART(PrintObj)  
};  
```  
  
 この宣言によって `CCmdTarget` 派生クラスが作成されます。  マクロ `DECLARE_INTERFACE_MAP` はこのクラスがカスタム インターフェイス マップを持つことをフレームワークに対して宣言します。  また、マクロ `BEGIN_INTERFACE_PART` とマクロ `END_INTERFACE_PART` は入れ子になったクラスを定義します。上の例では、入れ子になったクラスは CEditObj と CPrintObj です。入れ子になったクラス名の先頭には X が付きます。これに対してグローバル クラス名の先頭には "C"、インターフェイス クラス名の先頭には "I" が付きます。  これらの入れ子になった 2 つのクラスのそれぞれに、入れ子になった 2 つのメンバー m\_CEditObj と m\_CPrintObj が作成されます。  関数 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) はこれらのマクロによって自動的に宣言されるため、ここではそのインターフェイスに特有のメンバー関数 EditObject と PrintObject だけを宣言します。ターゲット プラットフォームに対する適切な `STDMETHOD` や仮想キーワードが与えられるように、OLE マクロ `_stdcall` が使用されています。  
  
 このクラスに対するインターフェイス マップを実装するには:  
  
```  
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)  
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)  
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)  
END_INTERFACE_MAP()  
```  
  
 これにより IID\_IPrintInterface IID と m\_CPrintObj、IID\_IEditInterface IID と m\_CEditObj が関連付けられます。  `CCmdTarget` 実装の [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) \(`CCmdTarget::ExternalQueryInterface`\) にはこのマップを使用し、要求があったときに m\_CPrintObj や m\_CEditObj へのポインターを返します。  `IID_IUnknown` に対するエントリをマップに含める必要はありません。`IID_IUnknown` が要求されると、マップの先頭のインターフェイス \(この場合は m\_CPrintObj\) が使用されます。  
  
 関数 `BEGIN_INTERFACE_PART`AddRef、[Release](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682317) はマクロ [によって自動的に宣言されますが、次のような記述が必要です。](http://msdn.microsoft.com/library/windows/desktop/ms682521)  
  
```  
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return pThis->ExternalAddRef();  
}  
  
ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return pThis->ExternalRelease();  
}  
  
HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(  
    REFIID iid, void FAR* FAR* ppvObj)  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return (HRESULT)pThis->ExternalQueryInterface(&iid, ppvObj);  
}  
  
void FAR EXPORT CEditPrintObj::XEditObj::EditObject()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    // code to "Edit" the object, whatever that means...  
}  
```  
  
 CEditPrintObj::CPrintObj の実装は、上の CEditPrintObj::CEditObj の定義に似ています。  ここに示した関数を自動的に生成するマクロを作成することも可能ですが \(開発初期バージョンの MFC\/OLE では実際に作成されていました\)、マクロが複数行に展開される場合はブレークポイントの設定が難しくなります。  このため、コードは手動で展開されます。  
  
 フレームワーク実装のメッセージ マップを利用すると、次の作業が不要になります。  
  
-   QueryInterface の実装  
  
-   AddRef と Release の実装  
  
-   各インターフェイスに対するこれらの組み込みメソッドの宣言  
  
 フレームワーク内部でもメッセージ マップが使用されています。  このため、フレームワーク クラス \(`COleServerDoc` など\) の派生クラスを作成すると、そのクラスは自動的に数種類のインターフェイスを持つことになります。また、このインターフェイスを変更したり、まったく新しいインターフェイスに置き換えたりすることもできます。  これは、フレームワークが基底クラスからのインターフェイス マップの継承を完全にサポートしているためです。  このため、`BEGIN_INTERFACE_MAP` は第 2 パラメーターとして基底クラス名を必要とします。  
  
> [!NOTE]
>  通常は、MFC から埋め込みに特殊化したインターフェイスを継承しても、MFC の組み込み OLE インターフェイスの実装を再利用できません。  これは、包含先の `METHOD_PROLOGUE` 派生オブジェクトへのアクセスに、マクロ `CCmdTarget` を使用しているためです。このマクロは *固定長* の派生オブジェクトからそこに埋め込まれているオブジェクトにアクセスするときに`CCmdTarget`のオフセット値を使用します。  たとえば `COleClientItem::XAdviseSink` では、MFC 実装から埋め込みの XMyAdviseSink を派生できません。これは XAdviseSink では、`COleClientItem` オブジェクトの先頭からのオフセット値が異なる値になるためです。  
  
> [!NOTE]
>  ただし、これらの関数に MFC の既定の動作を求めるときは、MFC 実装に処理を任せることができます。  これは `IOleInPlaceFrame` クラスで MFC 実装の `COleFrameHook` \(XOleInPlaceFrame\) によって行われます。このクラスは多くの関数に対して m\_xOleInPlaceUIWindow に処理を任せます。  この設計は、多数のインターフェイスを含むオブジェクトの実行時サイズを小さくする目的で選択されます。この処理ではバック ポインター \(前の m\_pParent など\) は不要です。  
  
### 集約とインターフェイス マップ  
 MFC はスタンドアロンの COM オブジェクトのほかに、集約もサポートしています。  集約自体については複雑すぎるためここでは説明しません。詳細については、[集約](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx)に関するトピックを参照してください。  ここではフレームワークとインターフェイス マップに組み込まれている集約に限定して説明します。  
  
 集約の利用方法には、\(1\) 集約をサポートする COM オブジェクトの利用、\(2\) 集約の一部となることができるオブジェクトの作成の 2 種類があります。  これらの機能はそれぞれ "集約オブジェクトの利用" と "集約可能オブジェクトの作成" と呼ばれます。  MFC ではこの両方がサポートされています。  
  
### 集約オブジェクトの利用  
 集約オブジェクトを使用するには、集約を QueryInterface 機構に結び付ける必要があります。  つまり、本体オブジェクトに最初から含まれているかのように集約オブジェクトを動作させる必要があります。  MFC のインターフェイス マップ機構にオブジェクトを結び付けるには、  マクロ `INTERFACE_PART` で入れ子になったオブジェクトを IID にリンクするほか、集約オブジェクトを `CCmdTarget` 派生クラスの一部として宣言します。  宣言には、`INTERFACE_AGGREGATE` マクロを使用します。  このマクロはメンバー変数 \([IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) オブジェクトまたはその派生クラスのオブジェクトへのポインター\) を指定してインターフェイス マップ機構に組み込むことができます。  `CCmdTarget::ExternalQueryInterface` を呼び出したときのポインターが NULL でなく、指定された [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) が `IID` オブジェクト自身がサポートする `IID` でない場合は、集約オブジェクトのメンバー関数 `CCmdTarget` が自動的に呼び出されます。  
  
##### マクロ INTERFACE\_AGGREGATE を使用するには  
  
1.  集約オブジェクトへのポインター \(`IUnknown*`\) となるメンバー変数を宣言します。  
  
2.  インターフェイス マップにマクロ `INTERFACE_AGGREGATE` を記述します。このマクロでこのメンバー変数を名前で指定します。  
  
3.  適切な時点で \(普通は `CCmdTarget::OnCreateAggregates` 内\) このメンバー変数を NULL 値以外の値に初期化します。  
  
 例:  
  
```  
class CAggrExample : public CCmdTarget  
{  
public:  
    CAggrExample();  
  
protected:  
    LPUNKNOWN m_lpAggrInner;  
    virtual BOOL OnCreateAggregates();  
  
    DECLARE_INTERFACE_MAP()  
    // "native" interface part macros may be used here  
};  
  
CAggrExample::CAggrExample()  
{  
    m_lpAggrInner = NULL;  
}  
  
BOOL CAggrExample::OnCreateAggregates()  
{  
    // wire up aggregate with correct controlling unknown  
    m_lpAggrInner = CoCreateInstance(CLSID_Example,  
        GetControllingUnknown(), CLSCTX_INPROC_SERVER,  
        IID_IUnknown, (LPVOID*)&m_lpAggrInner);  
    if (m_lpAggrInner == NULL)  
        return FALSE;  
    // optionally, create other aggregate objects here  
    return TRUE;  
}  
  
BEGIN_INTERFACE_MAP(CAggrExample, CCmdTarget)  
    // native "INTERFACE_PART" entries go here  
    INTERFACE_AGGREGATE(CAggrExample, m_lpAggrInner)  
END_INTERFACE_MAP()  
```  
  
 m\_lpAggrInner 変数はコンストラクターによって NULL に初期化されます。  既定の実装の [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) では、NULL 値のメンバー変数は無視されます。  集約オブジェクトは `OnCreateAggregates` で作成するのが適切です。  MFC 実装の `COleObjectFactory` 以外でオブジェクトを作成するときは、この関数を明示的に呼び出します。  `CCmdTarget::OnCreateAggregates` で集約オブジェクトを作成し、`CCmdTarget::GetControllingUnknown` を使用する理由は、集約可能オブジェクトの作成方法を解説する際に説明します。  
  
 上の方法を使用すると、オブジェクト本来のインターフェイスに加えて集約オブジェクトが持つすべてのインターフェイスを持つことができます。  集約オブジェクトがサポートするインターフェイスの一部だけを利用するには、`CCmdTarget::GetInterfaceHook` をオーバーライドします。  この方法では、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) と同じように、下位のフックが有効になります。  通常は、集約オブジェクトがサポートするすべてのインターフェイスを使用します。  
  
### 集約可能なオブジェクト実装のための作業  
 オブジェクトを集約可能にするには、[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) の処理を "controlling unknown" に任せる必要があります。 集約オブジェクトを相手のオブジェクトの一部にするには、[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) の処理を他の [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 派生オブジェクトに任せる必要があります。  この "controlling unknown" はオブジェクトが作成されるときにオブジェクト対して指定されます。つまり、`COleObjectFactory` の実装に対して指定されることになります。  COleObjectFactory をこのように実装すると、若干のオーバーヘッドが発生するため、場合によっては適切でない場合もあります。このため、MFC ではこの処理はオプションとして選択できるようになっています。  オブジェクトを集約可能にするには、そのオブジェクトのコンストラクターから `CCmdTarget::EnableAggregation` を呼び出します。  
  
 オブジェクトで集約を使用するときは、適切な "controlling unknown" が集約オブジェクトに渡されるようにする必要があります。  通常は、集約が作成されるときに [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ポインターがオブジェクトに渡されます。  たとえば、`CoCreateInstance` を使用してオブジェクトを作成すると、パラメーター pUnkOuter が "controlling unknown" になります。  正確な "controlling unknown" ポインターは、`CCmdTarget::GetControllingUnknown` を呼び出して取得できます。  しかし、コンストラクター中ではこの関数の戻り値は保証されません。  このため、集約オブジェクトは `CCmdTarget::OnCreateAggregates` をオーバーライドした関数の中でのみ作成することを推奨します。この中では \(`GetControllingUnknown` 実装から作成されたものであっても\) `COleObjectFactory` の戻り値は保証されます。  
  
 架空の参照カウントを作成または解放するときに、オブジェクトが正しい参照カウントを操作することも重要です。  これを保証するために、`ExternalAddRef` と `ExternalRelease` ではなく、必ず `InternalRelease` と `InternalAddRef` を呼び出すようにしてください。  集約をサポートするクラスで `InternalRelease` と `InternalAddRef` を呼び出すことはほとんどありません。  
  
### リファレンス マニュアル  
 独自のインターフェイスの定義や、フレームワークの OLE インターフェイスのオーバーライドなど、OLE の高度な機能を利用するときは、基盤となるインターフェイス マップ機構の使い方を理解しておく必要があります。  
  
 ここでは、このような高度な機能の実装に使用されるマクロと API について説明します。  
  
### CCmdTarget::EnableAggregation \- 関数の説明  
  
```  
  
void EnableAggregation();  
```  
  
## コメント  
 この種のオブジェクトについて OLE 集約をサポートする場合、この関数を派生クラスのコンストラクターで呼び出します。  この関数を呼び出すことによって、集約可能オブジェクトに必要な特別な IUnknown 実装が用意されます。  
  
### CCmdTarget::ExternalQueryInterface — 関数の説明  
  
```  
  
              DWORD ExternalQueryInterface(    const void FAR* lpIID,    LPVOID FAR* ppvObj   
);  
```  
  
## コメント  
  
#### パラメーター  
 `lpIID`  
 IID への far ポインター \(QueryInterface の第 1 引数\)  
  
 `ppvObj`  
 IUnknown\* へのポインター \(QueryInterface の第 2 引数\)  
  
## コメント  
 IUnknown を実装するとき、クラスが実装する各インターフェイスに対してこの関数を呼び出します。  この関数はオブジェクトのインターフェイス マップに基づき、標準的なデータ駆動型の QueryInterface を実行します。  この関数の戻り値は HRESULT 型にキャストする必要があります。  集約オブジェクトの場合、この関数はローカルなインターフェイス マップを使用せずに、"controlling IUnknown" を呼び出します。  
  
### CCmdTarget::ExternalAddRef \- 関数の説明  
  
```  
  
DWORD ExternalAddRef();  
```  
  
## コメント  
 IUnknown::AddRef を実装するとき、クラスが実装する各インターフェイスに対してこの関数を呼び出します。  戻り値は、CCmdTarget オブジェクトの新しい参照カウント値を示します。  集約オブジェクトの場合、この関数はローカルな参照カウントを操作せずに、"controlling IUnknown" を呼び出します。  
  
### CCmdTarget::ExternalRelease \- 関数の説明  
  
```  
  
DWORD ExternalRelease();  
  
```  
  
## コメント  
 IUnknown::Release を実装するとき、クラスが実装する各インターフェイスに対してこの関数を呼び出します。  戻り値は、オブジェクトの新しい参照カウント値を示します。  集約オブジェクトの場合、この関数はローカルな参照カウントを操作せずに、"controlling IUnknown" を呼び出します。  
  
### DECLARE\_INTERFACE\_MAP \- マクロの説明  
  
```  
  
DECLARE_INTERFACE_MAP  
  
```  
  
## コメント  
 このマクロは、`CCmdTarget` からの派生クラスのうち、インターフェイス マップを持つすべてのクラスで使用します。  使用方法は `DECLARE_MESSAGE_MAP` と同じです。  このマクロ呼び出しは、クラス定義 \(通常はヘッダー \(.H\) ファイル内\) で使用します。  `DECLARE_INTERFACE_MAP` を指定したクラスでは、実装ファイル \(.CPP\) でマクロ `BEGIN_INTERFACE_MAP` と `END_INTERFACE_MAP` を使用してインターフェイス マップを定義する必要があります。  
  
### BEGIN\_INTERFACE\_PART、END\_INTERFACE\_PART \- マクロの説明  
  
```  
  
              BEGIN_INTERFACE_PART(   
   localClass,  
   iface   
);  
END_INTERFACE_PART(   
   localClass   
)  
```  
  
## コメント  
  
#### パラメーター  
 l`ocalClass`  
 このインターフェイスを実装するクラスの名前  
  
 `iface`  
 このクラスによって実装されるインターフェイスの名前  
  
## コメント  
 クラスが実装するインターフェイスごとに、`BEGIN_INTERFACE_PART` と `END_INTERFACE_PART` のペアを記述する必要があります。  これらのマクロでは、OLE インターフェイスから派生させるローカル クラスと、そのクラスの埋め込みメンバー変数を定義します。  メンバー関数 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)、[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) は自動的に宣言されます。  これ以外のメンバー関数をインターフェイスで使用する場合は、直接宣言する必要があります。これらの宣言はマクロ `BEGIN_INTERFACE_PART` と `END_INTERFACE_PART` の間に記述します。  
  
 引数 `iface` は作成する OLE インターフェイス \(`IAdviseSink` や `IPersistStorage` など、またはカスタム インターフェイス\) を示します。  
  
 引数 `localClass` に定義するローカル クラス名を指定します。  名前の先頭には 'X' が自動的に付けられます。  この名前付け規則は、グローバル クラス名との競合を回避するためです。  また埋め込みメンバーには `localClass` 名の前に 'm\_x' を付けた名前が指定されます。  
  
 例:  
  
```  
BEGIN_INTERFACE_PART(MyAdviseSink, IAdviseSink)  
   STDMETHOD_(void,OnDataChange)(LPFORMATETC, LPSTGMEDIUM);  
   STDMETHOD_(void,OnViewChange)(DWORD, LONG);  
   STDMETHOD_(void,OnRename)(LPMONIKER);  
   STDMETHOD_(void,OnSave)();  
   STDMETHOD_(void,OnClose)();  
END_INTERFACE_PART(MyAdviseSink)  
```  
  
 これによって IAdviseSink から派生されるローカル クラス XMyAdviseSink が定義されます。またこのクラスのメンバー名は m\_xMyAdviseSink になります。  
  
> [!NOTE]
>  `STDMETHOD`\_ で始まる行は基本的に OLE2.H からコピーしたものであり、変更が加えられます。  OLE2.H からコピーすると、発見が困難なエラーを回避できます。  
  
### BEGIN\_INTERFACE\_MAP、END\_INTERFACE\_MAP \- マクロの説明  
  
```  
  
              BEGIN_INTERFACE_MAP(   
   theClass,  
   baseClass   
) END_INTERFACE_MAP  
```  
  
## コメント  
  
#### パラメーター  
 `theClass`  
 定義するインターフェイス マップが含まれるクラス  
  
 `baseClass`  
 `theClass` の派生元のクラス。  
  
## コメント  
 実際にインターフェイス マップを定義するには、実装ファイルにマクロ `BEGIN_INTERFACE_MAP` と `END_INTERFACE_MAP` を記述します。  実装するインターフェイスごとに 1 つ以上の `INTERFACE_PART` マクロを呼び出します。  このクラスで使用する集約ごとに 1 つの `INTERFACE_AGGREGATE` マクロ呼び出しを記述します。  
  
### INTERFACE\_PART \- マクロの説明  
  
```  
  
              INTERFACE_PART(   
   theClass,  
   iid,   
   localClass   
)  
```  
  
## コメント  
  
#### パラメーター  
 `theClass`  
 インターフェイス マップを持つクラスの名前。  
  
 `iid`  
 埋め込みクラスに割り当てられる `IID`。  
  
 `localClass`  
 ローカル クラスの名前。'X' は付けません。  
  
## コメント  
 このマクロはオブジェクトでサポートする各インターフェイスを定義する `BEGIN_INTERFACE_MAP` マクロと `END_INTERFACE_MAP` マクロの間で使用します。  このマクロは `theClass` と `localClass` で示されたクラスのメンバーに IID を割り当てます。  `localClass` の先頭には 'm\_x' が自動的に追加されます。  1 個のメンバーに複数の `IID` を割り当てることもできます。  これは、"最派生" インターフェイスを 1 個だけ作成し、これをすべての中間インターフェイスとして使用するときにも役に立ちます。  この方法を使用した例が `IOleInPlaceFrameWindow` インターフェイスです。  このインターフェイスの階層構造は次のようになっています。  
  
```  
IUnknown  
    IOleWindow  
        IOleUIWindow  
            IOleInPlaceFrameWindow  
```  
  
 `IOleInPlaceFrameWindow` を実装しているオブジェクトのクライアントは、実際に実装した "最派生" インターフェイス `QueryInterface` 以外に、`IOleUIWindow`、`IOleWindow`、[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) の各インターフェイスに対しても `IOleInPlaceFrameWindow` を適用できます。  この適用を処理するには、複数の `INTERFACE_PART` マクロを使用して、すべての基本インターフェイスを `IOleInPlaceFrameWindow` インターフェイスに割り当てます。  
  
 クラス定義ファイルには次のように記述されます。  
  
```  
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)  
```  
  
 クラス実装ファイルには次のように記述されます。  
  
```  
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)  
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)  
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)  
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)  
END_INTERFACE_MAP  
```  
  
 IUnknown は常に必要であるため、フレームワークによって自動的にサポートされます。  
  
### INTERFACE\_PART \- マクロの説明  
  
```  
  
              INTERFACE_AGGREGATE(   
   theClass,  
   theAggr   
)  
```  
  
## コメント  
  
#### パラメーター  
 `theClass`  
 インターフェイス マップを持つクラスの名前。  
  
 `theAggr`  
 集約するメンバー変数の名前。  
  
## コメント  
 このマクロは、クラスが集約オブジェクトを使用することをフレームワークに知らせます。  このマクロは `BEGIN_INTERFACE_PART` マクロと `END_INTERFACE_PART` マクロの間に記述します。  集約オブジェクトは [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) から派生した別のオブジェクトです。  集約と `INTERFACE_AGGREGATE` マクロを使用すると、集約によってサポートされているすべてのインターフェイスを、オブジェクトによって直接サポートされているように見せることができます。  引数 `theAggr` は [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) の直接または間接派生クラスのメンバー変数名です。  `INTERFACE_AGGREGATE` マクロをインターフェイス マップの中に記述するときは、必ず `INTERFACE_PART` マクロの後に記述します。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)