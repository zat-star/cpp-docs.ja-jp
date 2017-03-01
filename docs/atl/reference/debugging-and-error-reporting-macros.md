---
title: "デバッグと、エラー報告のマクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- macros, error reporting
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
caps.latest.revision: 18
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
ms.openlocfilehash: 112b43c325d4b73d2cc15ba41d9aac255c74da8a
ms.lasthandoff: 02/24/2017

---
# <a name="debugging-and-error-reporting-macros"></a>デバッグと、エラー報告のマクロ
これらのマクロは、デバッグとトレースに役立つ機能を提供します。  
  
|||  
|-|-|  
|[_ATL_DEBUG_INTERFACES](#_atl_debug_interfaces)|リークが発生するすべてのインターフェイスを出力ウィンドウに書き込みますが検出されたときに`_Module.Term`が呼び出されます。|  
|[_ATL_DEBUG_QI](#_atl_debug_qi)|すべての呼び出しを書き込みます`QueryInterface`アウトプット ウィンドウに表示します。|  
|[ATLASSERT](#atlassert)|同じ機能を実行、 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)マクロが C ランタイム ライブラリにあります。|  
|[ATLENSURE](#atlensure)|パラメーターの検証を実行します。 呼び出す`AtlThrow`が必要な場合|  
|[ATLTRACENOTIMPL](#atltracenotimpl)|指定した関数が実装されていません、ダンプ デバイスにメッセージを送信します。|  
|[ATLTRACE](http://msdn.microsoft.com/library/c796baa5-e2b9-4814-a27d-d800590b102e)|指定されたフラグとレベルに応じて、デバッガー ウィンドウなど、出力デバイスに警告を報告します。 旧バージョンと互換性のために含まれています。|  
|[ATLTRACE2](#atltrace2)|指定されたフラグとレベルに応じて、デバッガー ウィンドウなど、出力デバイスに警告を報告します。|  
  
##  <a name="a-nameatldebuginterfacesa--atldebuginterfaces"></a><a name="_atl_debug_interfaces"></a>_ATL_DEBUG_INTERFACES  
 ATL ヘッダー ファイルのすべてのトレースをインクルードする前にこのマクロを定義して`AddRef`と**リリース**出力ウィンドウに、コンポーネントのインターフェイスを呼び出します。  
  
```
#define _ATL_DEBUG_INTERFACES
```  
  
### <a name="remarks"></a>コメント  
 次に示すように、トレース出力が表示されます。  
  
 `ATL: QIThunk - 2008         AddRef  :   Object = 0x00d81ba0   Refcount = 1   CBug - IBug`  
  
 それぞれのトレースの最初の部分が必ず`ATL: QIThunk`します。 次に、特にを識別する値は、*インターフェイス サンク*使用されています。 インターフェイス サンクとは、参照カウントを維持し、ここで使用されるトレース機能を提供するために使用するオブジェクトです。 呼び出すたびに新しいインターフェイス サンクが作成された`QueryInterface`の要求を除き、 **IUnknown**インターフェイス (この場合は、同じサンクが返されますたびに COM の規則に準拠する)。  
  
 次にわかります`AddRef`または**リリース**呼び出されたメソッドを示します。 次に、そのインターフェイスの参照カウントが変更されたオブジェクトを識別する値が表示されます。 トレースされる値は、**この**オブジェクトのポインター。  
  
 トレースは、参照カウントが後にそのサンクの参照カウント`AddRef`または**リリース**呼び出されました。 この参照カウントがオブジェクトの参照カウントと一致しないことに注意してください。 各サンクは、COM の参照カウントの規則に完全に準拠するための独自の参照カウントを保持します。  
  
 追跡された情報の最後の部分は、オブジェクトと影響を受けているインターフェイスの名前、`AddRef`または**リリース**呼び出します。  
  
 サーバーがシャット ダウン時に検出リーク インターフェイスと`_Module.Term`が呼び出されますが次のようにログに記録します。  
  
 `ATL: QIThunk - 2005         LEAK    :   Object = 0x00d81ca0   Refcount = 1   MaxRefCount = 1   CBug - IBug`  
  
 ここで、前のトレース ステートメントで提供される情報に直接マップに指定した情報、インターフェイス サンクの有効期間全体を通じて、参照がカウントを調べることです。 さらに、そのインターフェイス サンク上最大の参照カウントを示す値を取得します。  
  
> [!NOTE]
> `_ATL_DEBUG_INTERFACES`製品版ビルドで使用できます。  
  
##  <a name="a-nameatldebugqia--atldebugqi"></a><a name="_atl_debug_qi"></a>_ATL_DEBUG_QI  
 すべての呼び出しを書き込みます`QueryInterface`アウトプット ウィンドウに表示します。  
  
```
#define _ATL_DEBUG_QI
```  
  
### <a name="remarks"></a>コメント  
 呼び出し`QueryInterface`失敗した場合、出力ウィンドウに表示されます。  
  
 *インターフェイス名* - `failed`  
  
##  <a name="a-nameatlasserta--atlassert"></a><a name="atlassert"></a>ATLASSERT  
 `ATLASSERT`マクロと同じ機能を実行する、 [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)マクロが C ランタイム ライブラリにあります。  
  
```
ATLASSERT(booleanExpression);
```  
  
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 0 以外の値または 0 に評価される式 (ポインターを含む)。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、`ATLASSERT`評価`booleanExpression`し、結果が false の場合は、デバッグ レポートを生成します。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldef.h  
    
##  <a name="a-nameatlensurea--atlensure"></a><a name="atlensure"></a>ATLENSURE  
 このマクロは、関数に渡されるパラメーターの検証に使用します。  
  
```
ATLENSURE(booleanExpression);
ATLENSURE_THROW(booleanExpression, hr);
```  
  
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 テストするブール式を指定します。  
  
 `hr`  
 返されるエラー コードを指定します。  
  
### <a name="remarks"></a>コメント  
 これらのマクロは、検出し、正しくないパラメーターの使用法をユーザーに通知するメカニズムを提供します。  
  
 マクロの呼び出し`ATLASSERT`条件には、呼び出しが失敗した場合と`AtlThrow`です。  
  
 **ATLENSURE**の場合も、`AtlThrow`が E_FAIL と共に呼び出されます。  
  
 **ATLENSURE_THROW**の場合も、`AtlThrow`を指定した HRESULT で呼び出されます。  
  
 違い**ATLENSURE**と`ATLASSERT`は**ATLENSURE**リリースでの例外はデバッグ ビルドと同様にもビルドがスローされます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&108;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_1.cpp)]  

## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  

##  <a name="a-nameatltracenotimpla--atltracenotimpl"></a><a name="atltracenotimpl"></a>ATLTRACENOTIMPL  
 ATL のデバッグ ビルドでは、文字列を送信"`funcname`は実装されていません"をダンプ デバイスを返す**E_NOTIMPL**します。  
  
```
ATLTRACENOTIMPL(funcname);
```  
  
### <a name="parameters"></a>パラメーター  
 `funcname`  
 [in]実装されていない関数の名前を表す文字列。  
  
### <a name="remarks"></a>コメント  
 リリース ビルドでは、単純に返します**E_NOTIMPL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#127;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltrace.h 

##  <a name="a-nameatla--atltrace"></a><a name="atl_"></a>ATLTRACE
 指定されたフラグとレベルに応じて、デバッガー ウィンドウなど、出力デバイスに警告を報告します。 旧バージョンと互換性のために含まれています。  
  
```
ATLTRACE(exp);

ATLTRACE(  
    DWORD category,
    UINT  level,
    LPCSTR lpszFormat, ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `exp`  
 [in]文字列と、Visual C に送信する変数ウィンドウまたはこれらのメッセージをトラップするアプリケーションを出力します。  
  
 `category`  
 [in]イベントまたはレポートをメソッドの型。 カテゴリの一覧については、「解説」を参照してください。  
  
 `level`  
 [in]レポートへのトレースのレベル。 詳細については、「解説」を参照してください。  
  
 `lpszFormat`  
 [in]ダンプ デバイスに送信する書式設定された文字列。  
  
### <a name="remarks"></a>コメント  
 参照してください[ATLTRACE2](#atltrace2)の詳細については**ATLTRACE**します。 **ATLTRACE**と`ATLTRACE2`同じ動作を持つ**ATLTRACE**は旧バージョンと互換性のために含まれます。  
  
##  <a name="a-nameatltrace2a--atltrace2"></a><a name="atltrace2"></a>ATLTRACE2  
 指定されたフラグとレベルに応じて、デバッガー ウィンドウなど、出力デバイスに警告を報告します。  
  
```
ATLTRACE2(exp);

ATLTRACE2(
    DWORD category,
    UINT level,
    LPCSTRlpszFormat,  ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `exp`  
 [in]Visual C の [出力] ウィンドウまたはこれらのメッセージをトラップするアプリケーションに送信する文字列。  
  
 `category`  
 [in]イベントまたはレポートをメソッドの型。 カテゴリの一覧については、「解説」を参照してください。  
  
 `level`  
 [in]レポートへのトレースのレベル。 詳細については、「解説」を参照してください。  
  
 `lpszFormat`  
 [in]`printf`-ダンプ デバイスに送信する文字列の作成に使用する書式指定文字列のスタイルを設定します。  
  
### <a name="remarks"></a>コメント  
 短い形式の`ATLTRACE2`デバッガーに文字列にはウィンドウの出力を書き込みます。 2 番目の形式の`ATLTRACE2`も、デバッガーの出力ウィンドウに出力を書き込みますが、ATL/MFC トレース ツールの設定が必要です (を参照してください[ATLTraceTool サンプル](../../visual-cpp-samples.md))。 例では、設定した場合の`level`を 4 レベル 0 ATL/MFC トレース ツールをしないメッセージが表示されます。 *レベル*0、1、2、3、または 4 にすることができます。 既定値は 0 では、最も重大な問題だけを報告します。  
  
 `category`パラメーターを設定するトレース フラグを一覧表示します。 これらのフラグは、レポートに方法の種類に対応します。 次の表は、使用できる有効なトレース フラグを一覧表示、`category`パラメーター。  
  
### <a name="atl-trace-flags"></a>ATL のトレース フラグ  
  
|ATL カテゴリ|説明|  
|------------------|-----------------|  
|`atlTraceGeneral`|ATL のすべてのアプリケーションをレポートします。 これが既定値です。|  
|`atlTraceCOM`|COM メソッドをレポートします。|  
|`atlTraceQI`|QueryInterface 呼び出しをレポートします。|  
|`atlTraceRegistrar`|オブジェクトの登録をレポートします。|  
|`atlTraceRefcount`|参照カウントの変更をレポートします。|  
|`atlTraceWindowing`|Windows の方法でのレポートたとえば、無効なメッセージ マップ ID を報告します。|  
|`atlTraceControls`|コントロールでのレポートたとえば、レポートをコントロールまたはそのウィンドウが破棄されるとします。|  
|`atlTraceHosting`|メッセージをホストしているレポートたとえば、コンテナー内のクライアントがアクティブになるを報告します。|  
|`atlTraceDBClient`|OLE DB コンシューマー テンプレート上のレポートたとえば、GetData 失敗した場合の呼び出し時に、出力は HRESULT を含めることができます。|  
|`atlTraceDBProvider`|OLE DB プロバイダー テンプレート上のレポートたとえば、列の作成が失敗したかどうかを報告します。|  
|`atlTraceSnapin`|MMC スナップイン アプリケーションについてレポートします。|  
|`atlTraceNotImpl`|レポートを指定された関数が実装されていません。|  
|**atlTraceAllocation**|メモリの atldbgmem.h のデバッグ ツールによって出力されるメッセージを報告します。|  
  
### <a name="mfc-trace-flags"></a>MFC のトレース フラグ  
  
|MFC のカテゴリ|説明|  
|------------------|-----------------|  
|**traceAppMsg**|一般的な目的は、MFC メッセージです。 常にお勧めします。|  
|**traceDumpContext**|メッセージは[CDumpContext](../../mfc/reference/cdumpcontext-class.md)します。|  
|**traceWinMsg**|MFC のメッセージの処理コードからのメッセージ。|  
|**traceMemory**|MFC のメモリ管理のコードからのメッセージ。|  
|**traceCmdRouting**|MFC のウィンドウからのメッセージはコマンド ルーティングのコードです。|  
|**traceHtml**|MFC の DHTML ダイアログ サポートからのメッセージ。|  
|**traceSocket**|MFC のソケットのサポートからのメッセージ。|  
|**traceOle**|MFC の OLE サポートからのメッセージ。|  
|**traceDatabase**|MFC データベース サポートからのメッセージ。|  
|**traceInternet**|MFC のインターネットからのメッセージをサポートします。|  
  
 カスタム トレース カテゴリを宣言するには、宣言のグローバル インスタンス、`CTraceCategory`クラスの次のようにします。  
  
 [!code-cpp[NVC_ATL_Utilities #&109;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_3.cpp)]  
  
 カテゴリ名、`MY_CATEGORY`に指定した名前は、この例では、`category`パラメーター。 最初のパラメーターは、ATL/MFC トレース ツールに表示されるカテゴリの名前です。 2 番目のパラメーターは、既定のトレース レベルです。 このパラメーターは省略可能で、既定のトレース レベルは 0 です。  
  
 ユーザー定義のカテゴリを使用します。  
  
 [!code-cpp[NVC_ATL_Utilities #&110;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_4.cpp)]  
  
 トレース メッセージをフィルター処理することを指定するには、前に Stdafx.h にこれらのマクロの定義を挿入、`#include <atlbase.h>`ステートメントです。  
  
 または、プリプロセッサ ディレクティブでフィルターを設定することができます、**プロパティ ページ** ダイアログ ボックス。 クリックして、**プリプロセッサ** タブで、グローバルに挿入し、**プリプロセッサの定義**ボックスを編集します。  
  
 Atlbase.h には既定の定義が含まれています、 `ATLTRACE2` atlbase.h が処理される前に、これらのシンボルを定義しない場合はマクロとこれらの定義が使用されます。  
  
 リリース ビルドで`ATLTRACE2`にコンパイルされる`(void) 0`します。  
  
 `ATLTRACE2`書式設定後に超える 1023 文字にダンプ デバイスに送信される文字列の内容を制限します。  
  
 **ATLTRACE**と`ATLTRACE2`同じ動作を持つ**ATLTRACE**は旧バージョンと互換性のために含まれます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&111;](../../atl/codesnippet/cpp/debugging-and-error-reporting-macros_5.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)   
 [デバッグとエラー報告に関するグローバル関数](../../atl/reference/debugging-and-error-reporting-global-functions.md)

