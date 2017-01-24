---
title: "テクニカル ノート 16: MFC における C++ の多重継承 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.inheritance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MI (多重継承)"
  - "多重継承, MFC のサポート"
  - "TN016"
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
caps.latest.revision: 22
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 16: MFC における C++ の多重継承
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、Microsoft Foundation Class との多重継承 \(MI\) を使用する方法について説明します。  MI を使用すると、MFC は必要ではありません。  MI は、MFC クラスでは使用されず、クラス ライブラリを作成する必要はありません。  
  
 次のサブトピックは MI がどのように MFC 共通の表現を使用して影響を与えたり、MI の一部を処理する方法について説明します。  これらの値の範囲は汎用 C\+\+ の制限です。  そのほかの MFC アーキテクチャによって課されます。  
  
 このテクニカル ノートの末尾に MI を使用する完全な MFC アプリケーションを検索します。  
  
## CRuntimeClass  
 MFC の永続性と動的オブジェクトを作成する機能はクラスを識別するために [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) のデータ構造を使用します。  MFC は、動的にこれらの構造やアプリケーションのシリアル化できるクラスの 1 を関連付けます。  これらの構造はアプリケーションが型 `AFX_CLASSINIT`の特別な静的オブジェクトを使用して起動時に初期化されます。  
  
 `CRuntimeClass` の現在の実装は MI の実行時の型情報をサポートしません。  ここでは、MFC アプリケーションで MI を使用できないわけではありません。  ただし、複数の基本クラスを持つオブジェクトを使用すると、特定の責任を負います。  
  
 [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) のメソッドは、複数の基本クラスがある場合、オブジェクトの型を判断します。  したがって、仮想基本クラスとして [CObject](../Topic/CObject%20Class.md) を使用できないため、C\+\+ が適切な関数呼び出しを区別できるように [CObject::Serialize](../Topic/CObject::Serialize.md) などの `CObject` のメンバー関数と [CObject::operator new](../Topic/CObject::operator%20new.md) への呼び出しはすべて、スコープの修飾子が必要です。  プログラムが MFC 内の MI を使用すると、`CObject` の基本クラスを含むクラスは、基本クラスのリストの左端のクラスである必要があります。  
  
 また、`dynamic_cast` の演算子を使用します。  基本クラスの 1 つがへの MI オブジェクトをキャストすると、コンパイラは、指定された基本クラスの関数を使用します。  詳細については、「[dynamic\_cast 演算子](../cpp/dynamic-cast-operator.md)」を参照してください。  
  
## CObject \-すべてのクラスのルート  
 すべての重要なクラスは `CObject`から直接的または間接的に派生します。  `CObject` に メンバー データがない場合、既定の機能があります。  MI を使用すると、複数の `CObject`\-派生クラスからその継承します。  クラスが [CFrameWnd](../mfc/reference/cframewnd-class.md) と [CObList](../mfc/reference/coblist-class.md)から継承する方法を次の例に示します。:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
 ...  
};  
CListWnd myListWnd;  
```  
  
 この場合 `CObject` は含まれる 2 です。  これは `CObject` のメソッドまたは演算子への参照を区別する方法が必要なことを意味します。  `operator new` と [演算子の削除](../Topic/CObject::operator%20delete.md) を区別する必要がある 2 個の演算子です。  別の例として、次のコードは、コンパイル時のエラーが発生する:  
  
```  
myListWnd.Dump(afxDump);  
    // compile time error, CFrameWnd::Dump or CObList::Dump ?  
```  
  
## Reimplementing CObject のメソッド  
 作成時に複数の `CObject` の新しいクラスは、他のユーザーに使用する基本クラスである必要があります `CObject` メソッド実装の派生しました。  `new` と `delete` 演算子は必須で、[ダンプ](../Topic/CObject::Dump.md) をお勧めします。  次の例では、再 `new` と `delete` の演算子と `Dump` のメソッド:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
public:  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    void Dump(CDumpContent& dc)  
        { CFrameWnd::Dump(dc);  
          CObList::Dump(dc); }  
     ...  
};  
```  
  
## CObject の仮想継承  
 これは、`CObject` を継承することで関数のあいまいさの問題を解決できるが、そうでないように見えることがあります。  `CObject`にメンバー データがないため、仮想継承が基本クラスのメンバー データの複数のコピーを作成する必要はありません。  前述した最初の例では `CFrameWnd` と `CObList`間で実装されるため、`Dump` の仮想メソッドがあいまいです。  あいまいさを削除する最良の方法は、前のセクションで説明したベスト プラクティスに従うことです。  
  
## CObject::IsKindOf と実行時の入力  
 `CObject` の MFC でサポートされるランタイムの機能は、マクロ `DECLARE_DYNAMIC`、`IMPLEMENT_DYNAMIC`、`DECLARE_DYNCREATE`、`IMPLEMENT_DYNCREATE`、`DECLARE_SERIAL` と `IMPLEMENT_SERIAL`を使用します。  これらのマクロは安全なダウンキャストを保証するために実行時の型のチェックを実行できます。  
  
 これらのマクロは、一つの基本クラスのみをサポートし、制限された方法での増加して継承クラスを使用できます。  ユーザーが `IMPLEMENT_DYNAMIC` で指定するか、`IMPLEMENT_SERIAL` は最初の \(または左端の\) 基本クラスと基本クラスです。  この配置は、左端の基本クラスだけの型チェックを有効にします。  実行時の型システムは追加基本クラスのは一切関知しません。  次の例では、ランタイム システムは `CFrameWnd`に対して型チェックをしますが、`CObList`に関するは一切関知しません。  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
    DECLARE_DYNAMIC(CListWnd)  
    ...  
};  
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)  
```  
  
## CWnd とメッセージ マップ  
 正しく動作する MFC メッセージ マップ システム用の 2 種類の追加要件があります:  
  
-   1 `CWnd`だけ派生の基本クラスです。  
  
-   `CWnd`\-派生の基本クラスは最初の \(または左端\) の基本クラスである必要があります。  
  
 操作の例を次に示します。:  
  
```  
class CTwoWindows : public CFrameWnd, public CEdit  
    { ... };  
        // error : two copies of CWnd  
  
class CListEdit : public CObList, public CEdit  
    { ... };  
        // error : CEdit (derived from CWnd) must be first  
```  
  
## MI を使用するサンプル プログラム  
 次の例では `CFrameWnd` と [CWinApp](../mfc/reference/cwinapp-class.md)から派生したクラスで、1 から構成されるスタンドアロン アプリケーションです。  ただし、アプリケーションを次のように構成しますが、これはクラスが 1 つある最小の MFC アプリケーションの例として、ことはお勧めしません。  
  
```  
#include <afxwin.h>  
  
class CHelloAppAndFrame : public CFrameWnd, public CWinApp  
{   
public:  
    CHelloAppAndFrame()  
        { }  
  
    // Necessary because of MI disambiguity  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    // Implementation  
    // CWinApp overrides  
    virtual BOOL InitInstance();  
    // CFrameWnd overrides  
    virtual void PostNcDestroy();  
    afx_msg void OnPaint();  
  
    DECLARE_MESSAGE_MAP()  
  
};  
  
BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)  
    ON_WM_PAINT()  
END_MESSAGE_MAP()  
  
// because the frame window is not allocated on the heap, we must  
// override PostNCDestroy not to delete the frame object  
void CHelloAppAndFrame::PostNcDestroy()  
{  
    // do nothing (do not call base class)  
}  
  
void CHelloAppAndFrame::OnPaint()  
{  
    CPaintDC dc(this);  
    CRect rect;  
    GetClientRect(rect);  
  
    CString s = "Hello, Windows!";  
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);  
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));  
    dc.SetBkMode(TRANSPARENT);  
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);  
}  
  
// Application initialization  
BOOL CHelloAppAndFrame::InitInstance()  
{  
    // first create the main frame  
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",  
        WS_OVERLAPPEDWINDOW, rectDefault))  
        return FALSE;  
  
    // the application object is also a frame window  
    m_pMainWnd = this;            
    ShowWindow(m_nCmdShow);  
    return TRUE;  
}  
  
CHelloAppAndFrame theHelloAppAndFrame;  
```  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)