---
title: "テクニカル ノート 39: MFC/OLE オートメーションの実装 | Microsoft Docs"
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
  - "オートメーション, MFC COM インターフェイス エントリ ポイント"
  - "IDispatch インターフェイス"
  - "MFC, COM サポート"
  - "MFC, および OLE DB"
  - "TN039"
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# テクニカル ノート 39: MFC/OLE オートメーションの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
## OLE IDispatch インターフェイスの概要  
 `IDispatch` インターフェイスは Visual Basic などの他のアプリケーション、またはそのほかの言語では、アプリケーションの機能を利用できるアプリケーションのメソッドとプロパティを受け取るように公開する方法です。  このインターフェイスの重要な部分を **IDispatch::Invoke** 関数です。  MFC は「 **IDispatch::Invoke**を実装するためにディスパッチ マップ」を使用します。  ディスパッチ マップは `CCmdTarget`\-派生クラスが、そのうちのレイアウトまたは「形状」に直接オブジェクトのプロパティを処理できるほか、または **IDispatch::Invoke** の要求を満たすためにオブジェクトのメンバー関数を呼び出しての MFC 実装について説明します。  
  
 ほとんどの場合、ClassWizard と MFC アプリケーションからは、OLE オートメーションの詳細の大部分を切り替えるように連携します。  プログラマは、実際の機能をアプリケーションに組み込むために集中し、基になる配管を気にする必要はありません。  
  
 ただし、MFC の動作にしていることを理解することが必要になるケースで場合もあります。  ここでは、フレームワークはメンバー関数とプロパティに **DISPID**s の割り当て方法に対応できます。  **DISPID**s を割り当てるためのアルゴリズム MFC の使用に関する情報は、アプリケーションのオブジェクトの「タイプ ライブラリ」を作成するときに ID を知る必要がある場合にのみ必要などです。  
  
## MFC DISPID の割り当て  
 オートメーション \(Visual Basic ユーザーなど\) のエンド ユーザーが、オートメーション プロパティの実際の名前とコードのメソッド \(obj.ShowWindow など\) を参照するが、**IDispatch::Invoke** の実装は実際の名前を受け取りません。  最適化の理由により、アクセスされるプロパティまたはメソッドを説明する、32 ビット「魔法のクッキー」である **DISPID**を受け取ります。  **DISPID** これらの値は `IDispatch` の実装から **IDispatch::GetIDsOfNames**という別のメソッドによって返されます。  オートメーション クライアント アプリケーションにアクセスする各プロパティまたはメンバーに対して `GetIDsOfNames` を一度呼び出す **IDispatch::Invoke**に遅く呼び出しの間をキャッシュします。  したがって、**IDispatch::Invoke** の呼び出しでオブジェクトの使用のみごとには、文字列の参照ではなく、一度に一度実行されます。  
  
 MFC は、次の 2 点に基づいて各メソッドとプロパティの **DISPID**s の確認:  
  
-   ディスパッチ マップ \(1 個の相対\) の先頭から間隔  
  
-   最派生クラス \(0 個の相対\) のディスパッチ マップの間隔  
  
 **DISPID** は 2 という二つの部分に分かれます。  **DISPID** の **LOWORD** は最初のコンポーネント、ディスパッチ マップの上端から間隔が含まれます。  **HIWORD** は最派生クラスからの距離が含まれます。  たとえば、次のようになります。  
  
```  
class CDispPoint : public CCmdTarget  
{  
public:  
    short m_x, m_y;  
    ...  
    DECLARE_DISPATCH_MAP()  
    ...  
};  
  
class CDisp3DPoint : public CDispPoint  
{  
public:  
    short m_z;  
    ...  
    DECLARE_DISPATCH_MAP()  
    ...  
};  
  
BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)  
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)  
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)  
END_DISPATCH_MAP()  
  
BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)  
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)  
END_DISPATCH_MAP()  
```  
  
 参照できるように、OLE オートメーション インターフェイスを公開するクラスが 2 つあります。  これらのクラスの 1 つが他から派生され、それによって、OLE オートメーションの部分 \(「x」および「y」プロパティこの場合\) など、基本クラスの機能を利用します。  
  
 MFC は次のとおり CDispPoint クラスの **DISPID**s を生成する:  
  
```  
property X    (DISPID)0x00000001  
property Y    (DISPID)0x00000002  
```  
  
 プロパティが基本クラスに存在しないため、**DISPID** の **HIWORD** は常になります \(CDispPoint の最派生クラスからの距離はゼロです。  
  
 MFC は次のとおり CDisp3DPoint クラスの **DISPID**s を生成する:  
  
```  
property Z    (DISPID)0x00000001  
property X    (DISPID)0x00010001  
property Y    (DISPID)0x00010002  
```  
  
 Z 軸のプロパティは、プロパティを公開するクラス、CDisp3DPoint で定義されているため、**HIWORD** の **DISPID** が与えられます。  X と Y のプロパティからこれらのプロパティを定義するクラスが最派生クラスで 1 種類の派生の間隔であるため、基本クラスでは、**DISPID** の **HIWORD** が 1 定義されます。  
  
> [!NOTE]
>  **LOWORD** はマップの位置によって、そのエントリに明示 **DISPID** マップであっても、常に決まります \(`DISP_PROPERTY` と `DISP_FUNCTION` マクロの **\_ID** バージョンについては、次のセクションを参照してください。  
  
## 高度な MFC ディスパッチ マップ機能  
 ClassWizard を Visual C\+\+ のこのバージョンにサポートしないいくつかの追加機能があります。  ClassWizard メソッドは、メンバー変数のプロパティ定義\/メンバー関数の構成プロパティをそれぞれ取得 `DISP_FUNCTION`、`DISP_PROPERTY`と `DISP_PROPERTY_EX` をサポートします。  これらの機能は、ほとんどのオートメーション サーバーを作成するには十分です。  
  
 次のマクロに ClassWizard でサポートされているマクロでは不十分な場合は使用できます。: `DISP_PROPERTY_NOTIFY`と `DISP_PROPERTY_PARAM`。  
  
## DISP\_PROPERTY\_NOTIFY — マクロの説明  
  
```  
  
        DISP_PROPERTY_NOTIFY(   
   theClass,   
   pszName,   
   memberName,   
   pfnAfterSet,   
   vtPropType   
)  
```  
  
## 解説  
  
### パラメーター  
 `theClass`  
 クラスの名前。  
  
 `pszName`  
 プロパティの外部名。  
  
 `memberName`  
 プロパティが格納されているメンバー変数の名前を指定します。  
  
 `pfnAfterSet`  
 プロパティが変更されたときに呼び出すメンバー関数の名前。  
  
 `vtPropType`  
 指定する値プロパティの型。  
  
## 解説  
 このマクロは `DISP_PROPERTY`とよく似ていますが、追加の引数を受け取ります。  引数は、*pfnAfterSet は、* 所在地 Nothing メンバー関数し、パラメーターを、「void な OnPropertyNotify \(\) 」になります。  これはメンバー変数が変更された **後** に呼び出されます。  
  
## DISP\_PROPERTY\_PARAM — マクロの説明  
  
```  
  
        DISP_PROPERTY_PARAM(   
   theClass,  
   pszName,  
   pfnGet,  
   pfnSet,  
   vtPropType,  
   vtsParams   
)  
```  
  
## 解説  
  
### パラメーター  
 `theClass`  
 クラスの名前。  
  
 `pszName`  
 プロパティの外部名。  
  
 `memberGet`  
 プロパティを取得するために使用されるメンバー関数の名前。  
  
 `memberSet`  
 プロパティの設定に使用されたメンバー関数の名前。  
  
 `vtPropType`  
 指定する値プロパティの型。  
  
 `vtsParams`  
 領域の文字列は、各パラメーターの VTS\_ をされています。  
  
## 解説  
 `DISP_PROPERTY_EX` マクロと同様に、このマクロは別でアクセスされるプロパティを取得し、メンバー関数設定を定義します。  このマクロは、プロパティのパラメーター リストを指定することができます。  これにより、他の方法でインデックス付きか、またはパラメーター化されたプロパティを実装する場合に便利です。  パラメーターはプロパティの値によって、その後に常に最初に配置されます。  たとえば、次のようになります。  
  
```  
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH,    VTS_I2 VTS_I2)  
```  
  
 構成メンバー関数は取得に対応し、P:  
  
```  
LPDISPATCH CMyObject::GetItem(short row, short col)  
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)  
```  
  
## DISP\_XXXX\_ID —マクロ説明  
  
```  
  
        DISP_FUNCTION_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnMember,  
   vtRetVal,  
   vtsParams   
) DISP_PROPERTY_ID(   
   theClass,  
   pszName,  
   dispid,  
   memberName,  
   vtPropType   
) DISP_PROPERTY_NOTIFY_ID(   
   theClass,  
   pszName,  
   dispid,  
   memberName,  
   pfnAfterSet,  
   vtPropType   
) DISP_PROPERTY_EX_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnGet,  
   pfnSet,  
   vtPropType   
) DISP_PROPERTY_PARAM_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnGet,  
   pfnSet,  
   vtPropType,  
   vtsParams   
)  
```  
  
## 解説  
  
### パラメーター  
 `theClass`  
 クラスの名前。  
  
 `pszName`  
 プロパティの外部名。  
  
 `dispid`  
 プロパティまたはメソッドの固定 DISPID。  
  
 `pfnGet`  
 プロパティを取得するために使用されるメンバー関数の名前。  
  
 `pfnSet`  
 プロパティの設定に使用されたメンバー関数の名前。  
  
 `memberName`  
 プロパティ マップにメンバー変数の名前  
  
 `vtPropType`  
 指定する値プロパティの型。  
  
 `vtsParams`  
 領域の文字列は、各パラメーターの VTS\_ をされています。  
  
## 解説  
 これらのマクロは、MFC を使用する代わりに **DISPID** を指定する自動的に 1 が代入されます。  これらの高度なマクロの名前が同じです。ただし、ID は、マクロ名が付きます \(たとえば。  **DISP\_PROPERTY\_ID**\) および ID は `pszName` パラメーターの直後に指定されたパラメーターによって決まります。  これらのマクロの詳細については、" AFXDISP.H を参照してください。  **\_ID** エントリはディスパッチ マップの末尾に配置する必要があります。  、マクロの**\_ID** 非バージョンと同様に **DISPID** の自動生成に影響を与えます \(**DISPID**s は位置によって決まります。  たとえば、次のようになります。  
  
```  
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)  
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)  
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)  
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)  
END_DISPATCH_MAP()  
```  
  
 MFC は次のとおり CDisp3DPoint クラスの DISPIDs を生成する:  
  
```  
property X    (DISPID)0x00020003  
property Y    (DISPID)0x00000002  
property Z     (DISPID)0x00000001  
```  
  
 固定 **DISPID** を指定できるようにする前に、既存のディスパッチ インターフェイス、または実装の特定のシステムで定義されているメソッドまたはプロパティに下位互換性です \(通常 **DISPID\_NEWENUM** のコレクションなどの負のな **DISPID**で示され、保持すると便利です。  
  
#### COleClientItem の IDispatch インターフェイスの取得  
 多数のサーバーは OLE サーバー機能とともにドキュメント オブジェクト内のオートメーションをサポートします。  このオートメーション インターフェイスへのアクセス権を得るには、直接 **COleClientItem::m\_lpObject** のメンバー変数にアクセスする必要があります。  次のコードは `COleClientItem`から派生されたオブジェクトの `IDispatch` インターフェイスを取得します。  この機能が必要とアプリケーションに次のコードを含めることができますが、T:  
  
```  
LPDISPATCH CMyClientItem::GetIDispatch()  
{  
    ASSERT_VALID(this);  
    ASSERT(m_lpObject != NULL);  
  
    LPUNKNOWN lpUnk = m_lpObject;  
  
    Run();    // must be running  
  
    LPOLELINK lpOleLink = NULL;  
    if (m_lpObject->QueryInterface(IID_IOleLink,   
        (LPVOID FAR*)&lpOleLink) == NOERROR)  
    {  
        ASSERT(lpOleLink != NULL);  
        lpUnk = NULL;  
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)  
        {  
            TRACE0("Warning: Link is not connected!\n");  
            lpOleLink->Release();  
            return NULL;  
        }  
        ASSERT(lpUnk != NULL);  
    }  
  
    LPDISPATCH lpDispatch = NULL;  
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch)   
        != NOERROR)  
    {  
        TRACE0("Warning: does not support IDispatch!\n");  
        return NULL;  
    }  
  
    ASSERT(lpDispatch != NULL);  
    return lpDispatch;  
}  
```  
  
 この関数から返されたディスパッチ インターフェイスは直接使用されるか `COleDispatchDriver` にタイプ セーフ アクセスに接続できます。  それを直接使用している場合は、マウス ポインターを持つを通じて **リリース** のメンバーを呼び出すとことを確認します。`COleDispatchDriver` のデストラクターはこれが既定になります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)