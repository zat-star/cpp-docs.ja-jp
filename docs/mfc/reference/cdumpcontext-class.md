---
title: "CDumpContext クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDumpContext
dev_langs:
- C++
helpviewer_keywords:
- CDumpContext class
- AfxDump object
- diagnostics, diagnostic classes
- diagnostic classes
- diagnosis, diagnostic classes
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 40d833772735e1079647f8f3205fb8db736843fd
ms.lasthandoff: 02/24/2017

---
# <a name="cdumpcontext-class"></a>CDumpContext クラス
人が読み取ることができる形式でテキストを出力するために、ストリームに依存した診断出力をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CDumpContext  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDumpContext::CDumpContext](#cdumpcontext)|`CDumpContext` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](#dumpashex)|16 進形式で指定されたアイテムをダンプします。|  
|[CDumpContext::Flush](#flush)|ダンプ コンテキスト バッファー内のデータをフラッシュします。|  
|[CDumpContext::GetDepth](#getdepth)|ダンプの深さに対応する整数値を取得します。|  
|[に](#hexdump)|16 進形式で配列に含まれるバイト数をダンプします。|  
|[CDumpContext::SetDepth](#setdepth)|ダンプの深さを設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CDumpContext::operator&lt;&lt;](#operator_lt_lt)|ダンプ コンテキストには、変数およびオブジェクトを挿入します。|  
  
## <a name="remarks"></a>コメント  
 `CDumpContext`基本クラスはありません。  
  
 使用する[afxDump](http://msdn.microsoft.com/library/4b3cfa3f-fb75-456a-9d99-a5601acbcb11)、あらかじめ宣言された`CDumpContext`ダンプのほとんどのオブジェクト。 `afxDump`オブジェクトは、Microsoft Foundation Class ライブラリのデバッグ バージョンでのみ使用できます。  
  
 メモリのいくつか[診断サービス](../../mfc/reference/diagnostic-services.md)を使用して`afxDump`出力にします。  
  
 Windows 環境の定義済みの出力の下`afxDump`、概念的に似たオブジェクト、`cerr`ストリーム、Windows の機能を使用して、デバッガーにルーティング**OutputDebugString**します。  
  
 `CDumpContext`クラスには、オーバー ロードされた挿入 ( ** << **) の演算子`CObject`オブジェクトのデータをダンプするポインター。 派生オブジェクトのカスタム ダンプ書式必要がある場合は、オーバーライド[CObject::Dump](../../mfc/reference/cobject-class.md#dump)します。 ほとんどの Microsoft Foundation クラスでオーバーライドされた実装`Dump`メンバー関数。  
  
 クラスから派生していない`CObject`など`CString`、 `CTime`、および`CTimeSpan`、独自のオーバー ロードがある`CDumpContext`などの操作を頻繁に使用される構造体としての挿入演算子**CFileStatus**、 `CPoint`、および`CRect`です。  
  
 使用する場合、 [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic)または[IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial)のクラスの実装でマクロ`CObject::Dump`の名前を出力、 `CObject`-クラスを派生します。 それ以外の場合、ように印刷される`CObject`します。  
  
 `CDumpContext`クラスは、ライブラリのデバッグとリリースの両方のバージョンで使用できますが、`Dump`メンバー関数は、デバッグ バージョンでのみ定義します。 使用**#ifdef _DEBUG**  /  `#endif`ステートメントなど、カスタム、診断コードを囲む`Dump`メンバー関数。  
  
 独自に作成する前に`CDumpContext`オブジェクトを作成する必要があります、`CFile`ダンプの宛先として機能するオブジェクト。  
  
 詳細については`CDumpContext`を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)します。  
  
 **#define _DEBUG define**  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDumpContext`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="a-namecdumpcontexta--cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a>CDumpContext::CDumpContext  
 クラスのオブジェクトを構築`CDumpContext`します。  
  
```  
CDumpContext(CFile* pFile = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFile`  
 ポインター、`CFile`ダンプの転送先となるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `afxDump`オブジェクトが自動的に作成します。  
  
 基になるにも書き込まれない`CFile`ダンプを干渉は、ダンプ コンテキストは、active 以外の場合は、です。 Windows 環境の下の出力は Windows の機能を使用して、デバッガーにルーティング**OutputDebugString**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#12;](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="a-namedumpashexa--cdumpcontextdumpashex"></a><a name="dumpashex"></a>CDumpContext::DumpAsHex  
 指定した型の&16; 進数として書式設定をダンプします。  
  
```  
CDumpContext& DumpAsHex(BYTE b);  
CDumpContext& DumpAsHex(DWORD dw);  
CDumpContext& DumpAsHex(int n);  
CDumpContext& DumpAsHex(LONG l);  
CDumpContext& DumpAsHex(LONGLONG n);  
CDumpContext& DumpAsHex(UINT u);  
CDumpContext& DumpAsHex(ULONGLONG n);  
CDumpContext& DumpAsHex(WORD w);
```  
  
### <a name="return-value"></a>戻り値  
 `CDumpContext` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 16 進数として指定した型の項目をダンプする場合は、このメンバー関数を呼び出します。 配列をダンプする[に](#hexdump)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#13;](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="a-nameflusha--cdumpcontextflush"></a><a name="flush"></a>CDumpContext::Flush  
 フォース ファイルに書き込まれるバッファーの残りの部分は、ダンプ コンテキストにアタッチされます。  
  
```  
void Flush();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#14;](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="a-namegetdeptha--cdumpcontextgetdepth"></a><a name="getdepth"></a>CDumpContext::GetDepth  
 簡易ダンプがプロセスになっているかどうかを判断します。  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 によって設定されたダンプの深さ`SetDepth`します。  
  
### <a name="example"></a>例  
  例を参照してください[SetDepth](#setdepth)します。  
  
##  <a name="a-namehexdumpa--cdumpcontexthexdump"></a><a name="hexdump"></a>に  
 16 進数として書式設定されたバイト配列にダンプします。  
  
```  
void HexDump(
    LPCTSTR lpszLine,  
    BYTE* pby,  
    int nBytes,  
    int nWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszLine*  
 新しい行の先頭に出力する文字列。  
  
 *pby*  
 ダンプするバイトを格納するバッファーへのポインター。  
  
 `nBytes`  
 ダンプするバイト数。  
  
 `nWidth`  
 バイトの最大数は、1 行 (出力行の幅は) にダンプします。  
  
### <a name="remarks"></a>コメント  
 16 進数として、特定の&1; つの項目の種類をダンプするを呼び出す[CDumpContext::DumpAsHex](#dumpashex)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#15;](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
##  <a name="a-nameoperatorltlta--cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a>CDumpContext::operator&lt;&lt;  
 ダンプ コンテキストを指定したデータを出力します。  
  
```  
CDumpContext& operator<<(const CObject* pOb);  
CDumpContext& operator<<(const CObject& ob);  
CDumpContext& operator<<(LPCTSTR lpsz);  
CDumpContext& operator<<(const void* lp);  
CDumpContext& operator<<(BYTE by);  
CDumpContext& operator<<(WORD w);  
CDumpContext& operator<<(DWORD dw);  
CDumpContext& operator<<(int n);  
CDumpContext& operator<<(double d);  
CDumpContext& operator<<(float f);  
CDumpContext& operator<<(LONG l);  
CDumpContext& operator<<(UINT u);  
CDumpContext& operator<<(LPCWSTR lpsz);  
CDumpContext& operator<<(LPCSTR lpsz);  
CDumpContext& operator<<(LONGLONG n);  
CDumpContext& operator<<(ULONGLONG n);  
CDumpContext& operator<<(HWND h);  
CDumpContext& operator<<(HDC h);  
CDumpContext& operator<<(HMENU h);  
CDumpContext& operator<<(HACCEL h);  
CDumpContext& operator<<(HFONT h);
```  
  
### <a name="return-value"></a>戻り値  
 A`CDumpContext`参照します。 戻り値を使用するには、ソース コードの&1; 行に複数の挿入を記述できます。  
  
### <a name="remarks"></a>コメント  
 に対して、挿入演算子がオーバー ロード`CObject`ほとんどのプリミティブ型の場合と同様のポインター。 文字列の内容のダンプに文字結果へのポインターポインター`void`のみアドレスの&16; 進数のダンプの結果します。 A **LONGLONG** 64 ビットの符号付き整数のダンプの結果A**使い**64 ビット符号なし整数のダンプが発生します。  
  
 使用する場合、`IMPLEMENT_DYNAMIC`または`IMPLEMENT_SERIAL`、クラス、挿入演算子の実装でマクロを`CObject::Dump`の名前を出力、 `CObject`-クラスを派生します。 それ以外の場合、ように印刷される`CObject`します。 オーバーライドする場合、`Dump`クラスの関数は、16 進数のダンプの代わりに、オブジェクトの内容のわかりやすい出力を提供できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&17;](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="a-namesetdeptha--cdumpcontextsetdepth"></a><a name="setdepth"></a>CDumpContext::SetDepth  
 ダンプの深さを設定します。  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>パラメーター  
 *nNewDepth*  
 新しい深さの値。  
  
### <a name="remarks"></a>コメント  
 プリミティブ型または単純にダンプしている場合`CObject`他のオブジェクトへのポインターが含まれていないし、0 の値で十分です。 0 を指定するすべてのオブジェクトが深いダンプより大きい値は、再帰的にダンプされます。 たとえば、コレクションの深いダンプがコレクションのすべての要素がダンプされます。 派生クラスでその他の特定の深さの値を使用することがあります。  
  
> [!NOTE]
>  循環参照は、深いダンプで検出されないされ、無限ループになることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#16;](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)

