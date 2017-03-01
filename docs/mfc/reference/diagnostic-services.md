---
title: "診断サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- diagnosis, diagnostic services
- diagnostic macros, list of general MFC
- services, diagnostic
- MFC, diagnostic services
- general diagnostic functions and variables
- diagnostics, diagnostic functions and variables
- diagnostics, list of general MFC
- diagnosis, diagnostic functions and variables
- diagnosis, list of general MFC
- general diagnostic macros in MFC
- diagnostic macros
- diagnostic services
- object diagnostic functions in MFC
- diagnostics, diagnostic services
- diagnostic functions and variables
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 86fe366a4d7863fb9339b7b5a9f880103876de33
ms.lasthandoff: 02/24/2017

---
# <a name="diagnostic-services"></a>診断サービス
Microsoft Foundation Class Library は、プログラムのデバッグをより簡単にする多くの診断サービスを提供します。 これらの診断サービスには、プログラムのメモリー割り振りを追跡したり、実行時にオブジェクトの内容をダンプしたり、実行時にデバッグ メッセージを表示したりできるようにするマクロやグローバル関数が含まれます。 診断サービスのマクロとグローバル関数は、次のカテゴリに分類されます。  
  
-   汎用診断マクロ  
  
-   汎用診断関数と変数  
  
-   オブジェクト診断関数  
  
 これらのマクロと関数は使用可能なから派生したすべてのクラスの`CObject`MFC のデバッグ構成とリリース バージョン。 ただしを除くすべて`DEBUG_NEW`と**を確認してください**リリース バージョンには影響しません。  
  
 デバッグ ライブラリ内の割り振られるすべてのメモリ ブロックは、一連の "ガード バイト" で囲まれます。 これらのバイトが間違ったメモリ書き込みによって乱される場合、診断ルーチンが問題を報告できます。 行:  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 実装ファイルのすべての呼び出し**新しい**メモリの割り当てが行わファイル名と行の数を格納します。 関数[CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince)メモリ リークを識別することができますこの余分な情報が表示されます。 クラスにも参照してください。 [CDumpContext](../../mfc/reference/cdumpcontext-class.md)診断出力の詳細についてはです。  
  
 さらに、C ランタイム ライブラリは、アプリケーションのデバッグに使用できる診断関数のセットもサポートしています。 詳細については、次を参照してください。[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)ランタイム ライブラリ リファレンスです。  
  
### <a name="mfc-general-diagnostic-macros"></a>MFC 汎用診断マクロ  
  
|||  
|-|-|  
|[アサート](#assert)|メッセージを表示し、指定された式と評価された場合、プログラムを中止**FALSE**ライブラリのデバッグ バージョンにします。|  
|[ASSERT_KINDOF](#assert_kindof)|オブジェクトが、指定されたクラスのオブジェクト、または指定されたクラスから派生したクラスのオブジェクトであることをテストします。|  
|[ASSERT_VALID](#assert_valid)|呼び出して、オブジェクトの内部の有効性をテスト、`AssertValid`メンバー関数は、通常オーバーライドされてから`CObject`します。|  
|[DEBUG_NEW](#debug_new)|デバッグ モードのすべてのオブジェクト割り当てにファイル名と行番号を指定します。これは、メモリー リークを見つけるのに役立ちます。|  
|[DEBUG_ONLY](#debug_only)|ような**ASSERT** ; 式の値はテストしませんが、デバッグ モードでのみ実行するコードに便利です。|  
|[TRACE](#trace)|提供`printf`のと同じライブラリのデバッグ バージョンで機能します。|  
|[確認します。](#verify)|ような**ASSERT**がデバッグ バージョンと同様にでも、ライブラリのリリース バージョンで式が評価されます。|  
  
### <a name="mfc-general-diagnostic-variables-and-functions"></a>MFC 汎用診断関数と変数  
  
|||  
|-|-|  
|[afxDump](#afxdump)|グローバル変数を送信する[CDumpContext](../../mfc/reference/cdumpcontext-class.md)やデバッグ ターミナル デバッガーの出力ウィンドウに情報。|  
|[afxMemDF](#afxmemdf)|デバッグ メモリ アロケーターの動作を制御するグローバル変数。|  
|[AfxCheckError](#afxcheckerror)|渡されたをテストするためのグローバル変数**SCODE**かどうかにエラーが発生し、適切なエラーをスローします。|  
|[AfxCheckMemory](#afxcheckmemory)|現在割り当てられているすべてのメモリの整合性を確認します。|  
|[AfxDump](#cdumpcontext_in_mfc_)|デバッガーにある間に呼び出さると、デバッグ中にオブジェクトの状態をダンプします。|  
|[AfxDumpStack](#afxdumpstack)|現在のスタックのイメージを生成します。 この関数は、常に、静的にリンクされます。|  
|[AfxEnableMemoryLeakDump](#afxenablememoryleakdump)|メモリ リーク ダンプを有効にします。|  
|[AfxEnableMemoryTracking](#afxenablememorytracking)|メモリのトラッキングをオンまたはオフにします。|  
|[AfxIsMemoryBlock](#afxismemoryblock)|メモリ ブロックが正しく割り当てられていることを確認します。|  
|[AfxIsValidAddress](#afxisvalidaddress)|メモリ アドレスの範囲がプログラムの境界内にあることを確認します。|  
|[AfxIsValidString](#afxisvalidstring)|文字列へのポインターが有効かどうかを判断します。|  
|[AfxSetAllocHook](#afxsetallochook)|各メモリ割り振りでの関数の呼び出しを有効にします。|  
  
### <a name="mfc-object-diagnostic-functions"></a>MFC オブジェクト診断関数  
  
|||  
|-|-|  
|[AfxDoForAllClasses](#afxdoforallclasses)|すべてで指定された関数を実行`CObject`-実行時型チェックをサポートするクラスを派生します。|  
|[AfxDoForAllObjects](#afxdoforallobjects)|すべてで指定された関数を実行`CObject`の派生クラスのオブジェクトに割り当てられた**新しい**します。|  
  
##  <a name="a-nameasserta--assert"></a><a name="assert"></a>アサート
 引数を評価します。  
  
```   
ASSERT(booleanExpression)   
```  
  
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 (ポインターの値を含む) または 0 以外に評価される式を指定します。  
  
### <a name="remarks"></a>コメント  
 結果が 0 の場合、マクロは診断メッセージを表示し、プログラムを中断します。 条件がゼロ以外の場合は、何もしません。  
  
 診断メッセージにフォームがあります  
  
 `assertion failed in file <name> in line <num>`  
  
 ここで*名*ソース ファイルの名前を指定し、 *num*ソース ファイルで失敗したアサーションの行番号は、です。  
  
 MFC のリリース バージョンで**ASSERT**式は評価されないとので、プログラムは停止しません。 環境に関係なく、式を評価する必要がある場合を使用して、**を確認してください**の代わりにマクロ**ASSERT**します。  
  
> [!NOTE]
>  この関数は MFC のデバッグ バージョンでのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&44;](../../mfc/codesnippet/cpp/diagnostic-services_2.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameassertkindofa--assertkindof"></a><a name="assert_kindof"></a>ASSERT_KINDOF  
 このマクロは、指されるオブジェクトは、指定したクラスのオブジェクトには、指定したクラスから派生したクラスのオブジェクトをアサートします。  
  
```   
ASSERT_KINDOF(classname, pobject)  
```  
  
### <a name="parameters"></a>パラメーター  
 *クラス名*  
 名前、 `CObject`-クラスを派生します。  
  
 *pobject*  
 クラス オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 *Pobject*パラメーター オブジェクトへのポインターがあります。 可能であり**const**します。 指されるオブジェクトとクラスをサポートする必要があります`CObject`ランタイム クラス情報。 たとえば、あることを確認する`pDocument`のオブジェクトへのポインター、`CMyDoc`クラス、またはその派生クラスのいずれかをコーディングできます。  
  
 [!code-cpp[NVC_MFCDocView #&194;](../../mfc/codesnippet/cpp/diagnostic-services_3.cpp)]  
  
 使用して、`ASSERT_KINDOF`マクロは、コーディングと同じでは正確にします。  
  
 [!code-cpp[NVC_MFCDocView #&195;](../../mfc/codesnippet/cpp/diagnostic-services_4.cpp)]  
  
 この関数の動作で宣言されたクラスに対してのみ、[DECLARE_DYNAMIC] (実行に時間-オブジェクト-モデル-services.md #declare_dynamic または[DECLARE_SERIAL](run-time-object-model-services.md#declare_serial)マクロです。  
  
> [!NOTE]
>  この関数は MFC のデバッグ バージョンでのみ使用できます。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameassertvalida--assertvalid"></a><a name="assert_valid"></a>ASSERT_VALID  
 使用すると、オブジェクトの内部状態の有効性に関する仮定をテストします。  
  
```   
ASSERT_VALID(pObject)   
```  
  
### <a name="parameters"></a>パラメーター  
 `pObject`  
 派生したクラスのオブジェクトを指定`CObject`のオーバーライド バージョンが使用されている、`AssertValid`メンバー関数。  
  
### <a name="remarks"></a>コメント  
 `ASSERT_VALID`呼び出し、`AssertValid`オブジェクトのメンバー関数は、その引数として渡されます。  
  
 MFC のリリース バージョンで`ASSERT_VALID`何も行われません。 デバッグ バージョンにポインターを検証、比較**NULL**、オブジェクトの独自の呼び出しと`AssertValid`メンバー関数。 同じ方法で警告メッセージが表示される場合、これらのテストが失敗するは、 [ASSERT](#assert)します。  
  
> [!NOTE]
>  この関数は MFC のデバッグ バージョンでのみ使用できます。  
  
 詳細と例については、次を参照してください。 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample&#19;](../../mfc/codesnippet/cpp/diagnostic-services_5.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="a-namedebugnewa--debugnew"></a><a name="debug_new"></a>DEBUG_NEW  
 メモリ リークの検出を支援します。  
  
```   
#define  new DEBUG_NEW   
```  
  
### <a name="remarks"></a>コメント  
 使用することができます`DEBUG_NEW`通常使用すると、プログラム内にあるすべての**新しい**ヒープ領域を割り当てる演算子。  
  
 デバッグ モードで (ときに、 **_DEBUG**シンボルが定義されている)、`DEBUG_NEW`のメモリを割り当てた各オブジェクトのファイル名と行番号を追跡します。 次に、使用、 [CMemoryState::DumpAllObjectsSince](cmemorystate-structure.md#dumpallobjectssince)メンバー関数で割り当てられた各オブジェクト`DEBUG_NEW`が割り当てられたファイル名と行の数で表示します。  
  
 使用する`DEBUG_NEW`、ソース ファイルに次のディレクティブを挿入します。  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 このディレクティブを挿入すると、プリプロセッサは挿入`DEBUG_NEW`任意の場所を使用する**新しい**MFC は、残りを実行します。 プログラムのリリース バージョンをコンパイルするときに`DEBUG_NEW`を単純な解決**新しい**操作、およびファイル名と行番号の情報は生成されません。  
  
> [!NOTE]
>  以前のバージョンの MFC (4.1 およびそれ以前) を配置する必要がある、`#define`ステートメントと呼ばれるすべてのステートメントの後に、`IMPLEMENT_DYNCREATE`または`IMPLEMENT_SERIAL`マクロです。 これは必要なくなりました。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="a-namedebugonlya--debugonly"></a><a name="debug_only"></a>DEBUG_ONLY  
 デバッグ モードで (ときに、 **_DEBUG**シンボルが定義されている)、`DEBUG_ONLY`引数を評価します。  
  
```   
DEBUG_ONLY(expression)   
```  
  
### <a name="remarks"></a>コメント  
 リリース ビルドで**DEBUG_ONLY**の引数を評価しません。 これは、機能は、デバッグ ビルドでのみ実行されるコードがある場合に便利です。  
  
 `DEBUG_ONLY`マクロは、周囲に相当*式*と**#ifdef _DEBUG**と`#endif`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#32;](../../mfc/codesnippet/cpp/diagnostic-services_6.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="a-nametracea--trace"></a><a name="trace"></a>トレース  
 指定した文字列を現在のアプリケーションのデバッガーに送信します。  
  
```   
TRACE(exp)  
TRACE(DWORD  category,  UINT  level, LPCSTR lpszFormat, ...)   
```  
  
### <a name="remarks"></a>コメント  
 参照してください[ATLTRACE2](http://msdn.microsoft.com/library/467ff555-e7a5-4f94-bdd9-50ee27ab9986)の詳細については**トレース**します。 **トレース**と`ATLTRACE2`同じように動作します。  
  
 MFC のデバッグ バージョンでは、このマクロは、指定した文字列を現在のアプリケーションのデバッガーに送信します。 リリース ビルドでは、このマクロは何も (コードが生成されないすべての) をコンパイルします。  
  
 詳細については、次を参照してください。 [MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="a-nameverifya--verify"></a><a name="verify"></a>確認します。  
 MFC のデバッグ バージョンでは、その引数を評価します。  
  
```   
VERIFY(booleanExpression)   
```  
  
### <a name="parameters"></a>パラメーター  
 `booleanExpression`  
 (ポインターの値を含む) または 0 以外に評価される式を指定します。  
  
### <a name="remarks"></a>コメント  
 結果が 0 の場合、マクロは診断メッセージを表示し、プログラムを停止します。 条件がゼロ以外の場合は、何もしません。  
  
 診断メッセージにフォームがあります  
  
 `assertion failed in file <name> in line <num>`  
  
 ここで*名*ソース ファイルの名前を指定し、 *num*ソース ファイルで失敗したアサーションの行番号は、です。  
  
 MFC のリリース バージョンで**確認**式を評価しますが、印刷していないプログラムを中断します。 たとえば、式が関数呼び出しの場合は、呼び出しになります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&198;](../../mfc/codesnippet/cpp/diagnostic-services_7.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="a-namecdumpcontextinmfca--afxdump-cdumpcontext-in-mfc"></a><a name="cdumpcontext_in_mfc_"></a>afxDump (MFC の CDumpContext)  
 アプリケーションでの基本的なオブジェクト ダンプ機能を提供します。  
  
```   
CDumpContext  afxDump;   
```  
  
### <a name="remarks"></a>コメント  
 `afxDump`定義済み[CDumpContext](../../mfc/reference/cdumpcontext-class.md)を送信できるようにするオブジェクト`CDumpContext`やデバッグ ターミナル デバッガーの出力ウィンドウに情報。 通常を指定する`afxDump`へのパラメーターとして`CObject::Dump`します。  
  
 Windows NT とすべてのバージョンの Windows`afxDump`出力は、アプリケーションをデバッグするときに、Visual C のデバッグ出力ウィンドウに送信します。  
  
 この変数は、MFC のデバッグ バージョンでのみ定義されます。 詳細については`afxDump`を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities 第&23;](../../mfc/codesnippet/cpp/diagnostic-services_8.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="a-nameafxmemdfa--afxmemdf"></a><a name="afxmemdf"></a>afxMemDF  
 この変数はデバッガーまたはプログラムからアクセス可能で、診断の割り当てを調整することができます。  
  
```   
int  afxMemDF;  
```  
  
### <a name="remarks"></a>コメント  
 `afxMemDF`列挙体で指定された次の値をとります`afxMemDF`:  
  
- **allocMemDF**デバッグ アロケーター (デバッグ ライブラリの既定の設定) をオンにします。  
  
- **delayFreeMemDF**メモリの解放を遅らせます。 プログラムがメモリ ブロックを解放中にアロケーターでは、基になるオペレーティング システムには、そのメモリは返しません。 プログラムの最大のメモリ負荷がかかります。  
  
- **checkAlwaysMemDF**呼び出し`AfxCheckMemory`たびにメモリを割り当てまたは解放します。 これにより、メモリの割り当てと解放は大幅に遅くなります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&30;](../../mfc/codesnippet/cpp/diagnostic-services_9.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="a-nameafxcheckerrora--afxcheckerror"></a><a name="afxcheckerror"></a>AfxCheckError  
 この関数に渡された**SCODE**するかどうかは、エラーを参照してください。  
  
```   
void AFXAPI AfxCheckError(SCODE sc);
throw CMemoryException* 
throw COleException*  
```  
  
### <a name="remarks"></a>コメント  
 エラーがある場合、関数は、例外をスローします。 場合は、渡された`SCODE`は**E_OUTOFMEMORY**、関数、[関数](../../mfc/reference/cmemoryexception-class.md)を呼び出して[AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)します。 それ以外の場合、関数、[関数](../../mfc/reference/coleexception-class.md)を呼び出して[AfxThrowOleException](exception-processing.md#afxthrowoleexception)します。  
  
 この関数は、アプリケーションで OLE 関数への呼び出しの戻り値を確認して使用できます。 アプリケーションでこの関数の戻り値をテストして最小限のコードでエラー状態に対応できます。  
  
> [!NOTE]
>  この関数では、同じ効果をデバッグし、非デバッグ ビルドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&33;](../../mfc/codesnippet/cpp/diagnostic-services_10.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h

##  <a name="a-nameafxcheckmemorya--afxcheckmemory"></a><a name="afxcheckmemory"></a>AfxCheckMemory  
 この関数は、空きメモリ プールを検証し、必要に応じて、エラー メッセージを出力します。  
  
```   
BOOL  AfxCheckMemory(); 
```  
  
### <a name="return-value"></a>戻り値  
 メモリ エラーがない場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数にメモリの破損が検出されない場合は、何も出力します。  
  
 によって割り当てられたも含め、ヒープに現在割り当てられているすべてのメモリ ブロックがチェックされます**新しい**などの直接の呼び出しを基になるメモリ アロケーターによって割り当てられたものではありませんが、`malloc`関数または**GlobalAlloc** Windows の機能です。 任意のブロックが壊れている可能性がある場合は、デバッガーの出力にメッセージが出力されます。  
  
 行を追加する場合  
  
 [!code-cpp[NVC_MFCCObjectSample&#14;](../../mfc/codesnippet/cpp/diagnostic-services_1.cpp)]  
  
 プログラム モジュールの場合、その後に続く呼び出しで`AfxCheckMemory`メモリが割り当てられたファイル名と行番号が表示されます。  
  
> [!NOTE]
>  かどうかには、独自のモジュールには、シリアル化可能なクラスの&1; つまたは複数の実装が含まれていますし、配置する必要があります、`#define`最後の行`IMPLEMENT_SERIAL`マクロの呼び出しです。  
  
 この関数は、MFC のデバッグ バージョンでのみ機能します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample #&26;](../../mfc/codesnippet/cpp/diagnostic-services_11.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
 
##  <a name="a-namemfca--afxdump-mfc"></a><a name="mfc_"></a>AfxDump (MFC)  
 デバッグ中に、オブジェクトの状態をダンプするデバッガーでは、この関数を呼び出します。  
  
```   
void AfxDump(const CObject* pOb); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pOb`  
 派生したクラスのオブジェクトへのポインター`CObject`します。  
  
### <a name="remarks"></a>コメント  
 **AfxDump**呼び出し、オブジェクトの`Dump`メンバー関数は、指定した場所に情報を送信、`afxDump`変数です。 **AfxDump** MFC のデバッグ バージョンでのみ使用できます。  
  
 プログラム コードを呼び出さないように**AfxDump**、代わりに呼び出す必要がありますが、`Dump`適切なオブジェクトのメンバー関数。  
  
##  <a name="a-nameafxdumpstacka--afxdumpstack"></a><a name="afxdumpstack"></a>AfxDumpStack  
 現在のスタックのイメージを生成する、このグローバル関数を使用できます。  
  
```   
void AFXAPI AfxDumpStack(DWORD dwTarget = AFX_STACK_DUMP_TARGET_DEFAULT); 
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTarget*  
 ダンプの出力先を示します。 可能な値は、ビットごとの OR を使用して結合することができます ( **|**) 演算子は次のようにします。  
  
- **AFX_STACK_DUMP_TARGET_TRACE**の出力を送信、[トレース](#trace)マクロです。 **トレース**マクロでは、デバッグ ビルドにのみ出力が生成されます。 リリース ビルドで出力を生成しません。 また、**トレース**デバッガー以外のターゲットにリダイレクトすることができます。  
  
- **AFX_STACK_DUMP_TARGET_DEFAULT**送信は、既定のターゲットへの出力をダンプします。 デバッグ ビルドは出力に送ら、**トレース**マクロです。 リリース ビルドでは、出力はクリップボードに移動します。  
  
- **AFX_STACK_DUMP_TARGET_CLIPBOARD**クリップボードのみに出力を送信します。 使用してプレーン テキストとしてクリップボードにデータを配置、**エディット**クリップボードの形式です。  
  
- **AFX_STACK_DUMP_TARGET_BOTH**クリップボードにされ、出力を送信、**トレース**マクロ、同時にします。  
  
- **出力が**Win32 関数を使用して出力をデバッガーに直接送信**OutputDebugString()**します。 このオプションは両方のデバッグでのデバッグ出力を生成し、プロセスにデバッガーがアタッチされている場合、リリース ビルドします。 **出力が**(アタッチされている場合、デバッガーを常に到達し、リダイレクトすることはできません。  
  
### <a name="remarks"></a>コメント  
 次の例は、呼び出しから生成された出力の&1; つの行を反映`AfxDumpStack`MFC ダイアログ アプリケーション ボタン ハンドラーから。  
  
 `=== begin AfxDumpStack output ===`  
  
 `00427D55: DUMP2\DEBUG\DUMP2.EXE! void AfxDumpStack(unsigned long) + 181 bytes`  
  
 `0040160B: DUMP2\DEBUG\DUMP2.EXE! void CDump2Dlg::OnClipboard(void) + 14 bytes`  
  
 `0044F884: DUMP2\DEBUG\DUMP2.EXE! int _AfxDispatchCmdMsg(class CCmdTarget *,`  
  
 `unsigned int,int,void ( CCmdTarget::*)(void),void *,unsigned int,struct AFX_CMDHANDLE`  
  
 `0044FF7B: DUMP2\DEBUG\DUMP2.EXE! virtual int CCmdTarget::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 626 bytes`  
  
 `00450C71: DUMP2\DEBUG\DUMP2.EXE! virtual int CDialog::OnCmdMsg(unsigned`  
  
 `int,int,void *,struct AFX_CMDHANDLERINFO *) + 36 bytes`  
  
 `00455B27: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnCommand(unsigned`  
  
 `int,long) + 312 bytes`  
  
 `00454D3D: DUMP2\DEBUG\DUMP2.EXE! virtual int CWnd::OnWndMsg(unsigned`  
  
 `int,unsigned int,long,long *) + 83 bytes`  
  
 `00454CC0: DUMP2\DEBUG\DUMP2.EXE! virtual long CWnd::WindowProc(unsigned`  
  
 `int,unsigned int,long) + 46 bytes`  
  
 `004528D9: DUMP2\DEBUG\DUMP2.EXE! long AfxCallWndProc(class CWnd *,struct`  
  
 `HWND__ *,unsigned int,unsigned int,long) + 237 bytes`  
  
 `00452D34: DUMP2\DEBUG\DUMP2.EXE! long AfxWndProc(struct HWND__ *,unsigned`  
  
 `int,unsigned int,long) + 129 bytes`  
  
 `BFF73663: WINDOWS\SYSTEM\KERNEL32.DLL! ThunkConnect32 + 2148 bytes`  
  
 `BFF928E0: WINDOWS\SYSTEM\KERNEL32.DLL! UTUnRegister + 2492 bytes`  
  
 `=== end AfxDumpStack() output ===`  
  
 上記の出力の各行は、最後の関数呼び出し、関数呼び出しと呼ばれる関数のプロトタイプを含むモジュールの完全なパス名のアドレスを示します。 関数の指定したアドレスで、スタック上の関数呼び出しが発生しない場合は、バイト単位のオフセットが表示されます。  
  
 たとえば、次の表では、上記の出力の最初の行について説明します。  
  
|出力|説明|  
|------------|-----------------|  
|`00427D55:`|最後の関数呼び出しの戻りアドレス。|  
|`DUMP2\DEBUG\DUMP2.EXE!`|関数呼び出しを含むモジュールの完全なパス名。|  
|`void AfxDumpStack(unsigned long)`|関数プロトタイプと呼ばれます。|  
|`+ 181 bytes`|関数プロトタイプのアドレスからバイト単位のオフセット (この場合、 `void AfxDumpStack(unsigned long)`) リターン アドレスを (この場合、 `00427D55`)。|  
  
 `AfxDumpStack`MFC ライブラリのデバッグおよび非デバッグ バージョンであります。ただし、実行可能ファイルの共有 DLL で MFC を使用している場合でもは、関数は静的にリンクされることは常にされます。 共有ライブラリの実装では、関数は mfcs42 です。LIB ライブラリ (とそのバリアント)。  
  
 この関数を適切に使用します。  
  
-   IMAGEHLP ファイルです。DLL がパスにする必要があります。 この DLL がない、関数により、エラー メッセージが表示されます。 参照してください[イメージ ヘルプ ライブラリ](http://msdn.microsoft.com/library/windows/desktop/ms680321)IMAGEHLP によって提供される関数のセットについてです。  
  
-   スタックにフレームを持つモジュールは、デバッグ情報を含める必要があります。 デバッグ情報を含んでいない場合、は、スタック トレースでは、関数によって生成されますが、トレースがあまり詳しく説明します。  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameafxenablememoryleakdumpa--afxenablememoryleakdump"></a><a name="afxenablememoryleakdump"></a>AfxEnableMemoryLeakDump  
 `AFX_DEBUG_STATE` デストラクター内のメモリ リーク ダンプを有効または無効にします。  
  
```  
BOOL AFXAPI AfxEnableMemoryLeakDump(BOOL bDump);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bDump`  
 `TRUE` はメモリ リーク ダンプが有効なことを示し、`FALSE` はメモリ リーク ダンプが無効なことを示します。  
  
### <a name="return-value"></a>戻り値  
 このフラグの以前の値。  
  
### <a name="remarks"></a>コメント  
 アプリケーションが MFC ライブラリをアンロードしたときに、MFC ライブラリがメモリ リークを確認します。 ユーザーに、メモリ リークを報告するこの時点で、**デバッグ**のウィンドウ[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]です。  
  
 アプリケーションが MFC ライブラリの前に別のライブラリを読み込んだ場合、そのライブラリ内の一部のメモリ割り当てが誤ってメモリ リークとして報告されます。 誤ったメモリ リークが原因で、MFC ライブラリがそれらを報告したときに、アプリケーションがゆっくりと終了する可能性があります。 このような場合、 `AfxEnableMemoryLeakDump` を使用してメモリ リーク ダンプを無効にします。  
  
> [!NOTE]
>  この方法を使用してメモリ リーク ダンプをオフにすると、アプリケーションで有効なメモリ リークのレポートを受け取らなくなります。 この方法を使用するのは、メモリ リーク ダンプに誤ったメモリ リークが含まれているという確信がある場合のみにする必要があります。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameafxenablememorytrackinga--afxenablememorytracking"></a><a name="afxenablememorytracking"></a>AfxEnableMemoryTracking  
 通常、診断メモリ追跡は MFC のデバッグ バージョンで有効にします。  
  
```   
BOOL AfxEnableMemoryTracking(BOOL bTrack); 
```  
  
### <a name="parameters"></a>パラメーター  
 *bTrack*  
 この値を設定**TRUE**メモリは追跡がオン**FALSE**をオフにします。  
  
### <a name="return-value"></a>戻り値  
 追跡を有効にフラグの以前の設定です。  
  
### <a name="remarks"></a>コメント  
 正しくブロックを割り当てていることがわかっているコードのセクションでの追跡を無効にするのにには、この関数を使用します。  
  
 詳細については`AfxEnableMemoryTracking`を参照してください[MFC アプリケーションのデバッグ](/visualstudio/debugger/mfc-debugging-techniques)します。  
  
> [!NOTE]
>  この関数は、MFC のデバッグ バージョンでのみ機能します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&24;](../../mfc/codesnippet/cpp/diagnostic-services_12.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameafxismemoryblocka--afxismemoryblock"></a><a name="afxismemoryblock"></a>AfxIsMemoryBlock  
 テストの診断のバージョンによって割り当てられたメモリの現在アクティブなブロックを表すかどうかを確認するメモリ アドレス**新しい**します。  
  
```   
BOOL AfxIsMemoryBlock(
    const void* p,  
    UINT nBytes,  
    LONG* plRequestNumber = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 テストするメモリ ブロックへのポインター。  
  
 `nBytes`  
 メモリ ブロックのバイトの長さが含まれています。  
  
 `plRequestNumber`  
 指す、**長い**整数は、そのメモリ ブロックの割り当てのシーケンス番号を使用して入力するか、現在アクティブなメモリ ブロックを表していない場合は&0; です。  
  
### <a name="return-value"></a>戻り値  
 メモリ ブロックが現在割り当てられているし、長さが正しい場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 また、元の割り当てられたサイズに対して指定したサイズも確認します。 割り当て順序番号が返される場合は、関数は&0; 以外の値を返す`plRequestNumber`します。 この番号は、ブロックが他のすべての基準が割り当てられる順序を表す**新しい**割り当てします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&27;](../../mfc/codesnippet/cpp/diagnostic-services_13.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameafxisvalidaddressa--afxisvalidaddress"></a><a name="afxisvalidaddress"></a>AfxIsValidAddress  
 プログラムのメモリ空間内に完全に収まっていることを確認するには、すべてメモリ アドレスをテストします。  
  
```   
BOOL AfxIsValidAddress(
    const void* lp,  
    UINT nBytes,  
    BOOL bReadWrite = TRUE); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lp`  
 テストするメモリのアドレスへのポインター。  
  
 `nBytes`  
 テストするメモリのバイト数が含まれています。  
  
 *bReadWrite*  
 メモリが読み取りと書き込みの両方があるかどうかを指定します ( **TRUE**) か、または読み込み ( **FALSE**)。  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、指定されたメモリ ブロックの場合は 0 以外に含まれる完全プログラムのメモリ領域です。それ以外の場合 0 を返します。  
  
 非デバッグ ビルドでは、0 以外の値`lp`NULL、0 以外ではありません。  
  
### <a name="remarks"></a>コメント  
 アドレスが割り当てられたブロックに制限がない**新しい**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&28;](../../mfc/codesnippet/cpp/diagnostic-services_14.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameafxisvalidstringa--afxisvalidstring"></a><a name="afxisvalidstring"></a>AfxIsValidString  
 文字列へのポインターが有効かどうかを判断するのにには、この関数を使用します。  
  
```   
BOOL  AfxIsValidString(
    LPCSTR lpsz,  
    int nLength = -1); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 テストへのポインター。  
  
 `nLength`  
 バイト単位でテストする文字列の長さを指定します。 値の â € の"1 を示し、文字列が null で終端することです。  
  
### <a name="return-value"></a>戻り値  
 デバッグ ビルドで、指定したサイズの文字列を指定したポインターが指している場合は 0 以外。それ以外の場合 0 を返します。  
  
 非デバッグ ビルドでは、0 以外の値`lpsz`NULL、0 以外ではありません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&29;](../../mfc/codesnippet/cpp/diagnostic-services_15.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameafxsetallochooka--afxsetallochook"></a><a name="afxsetallochook"></a>AfxSetAllocHook  
 各メモリ ブロックが割り当てられる前に、指定された関数の呼び出しをできるようにするフックを設定します。  
  
```   
AFX_ALLOC_HOOK AfxSetAllocHook(AFX_ALLOC_HOOK pfnAllocHook); 
```  
  
### <a name="parameters"></a>パラメーター  
 *pfnAllocHook*  
 呼び出す関数の名前を指定します。 割り当て関数のプロトタイプについて、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 割り当てを許可する場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Microsoft Foundation Class ライブラリのデバッグ メモリ アロケーターは、メモリの割り当てを監視して、割り当てが許可されているかどうかを制御するユーザーを許可するようにユーザー定義フック関数を呼び出すことができます。 割り当てフック関数は通りプロトタイプ宣言があります。  
  
 **BOOL AFXAPI AllocHook( size_t** `nSize`**, BOOL** `bObject`**, LONG** `lRequestNumber` **);**  
  
 `nSize`  
 提案されたメモリ割り当てのサイズ。  
  
 `bObject`  
 **TRUE**割り当てがある場合、 `CObject`-派生オブジェクト。 それ以外の場合**FALSE**します。  
  
 `lRequestNumber`  
 メモリ割り当てのシーケンス番号。  
  
 なお、 **AFXAPI**呼び出し規約には、呼び出し先がスタックからパラメーターを削除する必要があることを意味します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameafxdoforallclassesa--afxdoforallclasses"></a><a name="afxdoforallclasses"></a>AfxDoForAllClasses  
 すべてシリアル化可能なために、指定されたイテレーション関数を呼び出して`CObject`-アプリケーションのメモリ空間内のクラスを派生します。  
  
```   
void  
AFXAPI AfxDoForAllClasses(
    void (* pfn)(const CRuntimeClass* pClass, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pfn`  
 各クラスに対して呼び出される反復関数へのポインター。 関数の引数がへのポインター、`CRuntimeClass`オブジェクトと、呼び出し元が関数に提供する追加のデータへの void ポインターです。  
  
 `pContext`  
 呼び出し元は、反復関数に提供できる省略可能なデータへのポインター。 このポインターは、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 シリアル化可能な`CObject`の派生クラスは、クラスの派生を使用して、`DECLARE_SERIAL`マクロです。 渡されるポインター`AfxDoForAllClasses`で`pContext`が呼び出されるたびに指定されたイテレーション関数に渡されます。  
  
> [!NOTE]
>  この関数は、MFC のデバッグ バージョンでのみ機能します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&113;](../../mfc/codesnippet/cpp/diagnostic-services_16.cpp)]  
  
 [!code-cpp[NVC_MFCCollections #&114;](../../mfc/codesnippet/cpp/diagnostic-services_17.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="a-nameafxdoforallobjectsa--afxdoforallobjects"></a><a name="afxdoforallobjects"></a>AfxDoForAllObjects  
 派生したすべてのオブジェクトの指定されたイテレーション関数を実行`CObject`使って割り当てられた**新しい**します。  
  
```   
void AfxDoForAllObjects(
    void (* pfn)(CObject* pObject, void* pContext),  
    void* pContext); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pfn`  
 各オブジェクトに対して実行する反復関数へのポインター。 関数の引数がへのポインター、`CObject`と、呼び出し元が関数に提供する追加のデータへの void ポインターです。  
  
 `pContext`  
 呼び出し元は、反復関数に提供できる省略可能なデータへのポインター。 このポインターは、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 スタック、グローバル、または埋め込みオブジェクトは列挙されません。 渡されるポインター`AfxDoForAllObjects`で`pContext`が呼び出されるたびに指定されたイテレーション関数に渡されます。  
  
> [!NOTE]
>  この関数は、MFC のデバッグ バージョンでのみ機能します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&115;](../../mfc/codesnippet/cpp/diagnostic-services_18.cpp)]  
  
 [!code-cpp[NVC_MFCCollections&116; 位](../../mfc/codesnippet/cpp/diagnostic-services_19.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
