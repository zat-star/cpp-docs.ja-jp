---
title: "デバッグ ルーチン | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "デバッグ [CRT]、マクロ"
  - "マクロ、デバッグ"
  - "デバッグ ルーチン"
  - "デバッグ マクロ"
  - "デバッグ [CRT]、ランタイム ルーチン"
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# デバッグ ルーチン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C ランタイム ライブラリのデバッグ バージョンには、プログラムのデバッグを容易にする多くの診断サービスが用意されており、開発者は次のことが可能になります。  
  
-   デバッグ中にランタイム関数に直接ステップ インする  
  
-   アサーション、エラー、および例外を解決する  
  
-   ヒープ割り当てを追跡し、メモリ リークを防ぐ  
  
-   ユーザーにデバッグ メッセージを報告する  
  
 これらのルーチンを使用するには、[\_DEBUG](../Topic/_DEBUG.md) フラグを定義する必要があります。  これらのルーチンはすべて、アプリケーションの製品版ビルドでは何も行いません。  新しいデバッグ ルーチンの使用方法の詳細については、「[CRT のデバッグ技術](../Topic/CRT%20Debugging%20Techniques.md)」を参照してください。  
  
### C ランタイム ライブラリ ルーチンのデバッグ バージョン  
  
|ルーチン|使用方法|同等の .NET Framework 関数|  
|----------|----------|---------------------------|  
|[\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)|式を評価し、結果が FALSE の場合はデバッグ レポートを生成します|[\<caps:sentence id\="tgt15" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)|`_ASSERT` に似ていますが、生成されるレポートに失敗した式が含まれます|[\<caps:sentence id\="tgt18" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|デバッグ ヒープに割り当てられたメモリ ブロックの整合性を確認します|[\<caps:sentence id\="tgt20" sentenceid\="e42975224af21ff11a761e6a6bdbd602" class\="tgtSentence"\>System::Diagnostics::PerformanceCounter\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)|  
|[\_CrtDbgBreak](../Topic/_CrtDbgBreak.md)|ブレークポイントを設定します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtDbgReport、\_CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|ユーザー メッセージのあるデバッグ レポートを生成し、3 つの宛先にレポートを送信します|[System::Diagnostics::Debug::Write](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.write.aspx)、[System::Diagnostics::Debug::Writeline](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeline.aspx)、[System::Diagnostics::Debug::WriteIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeif.aspx)、[System::Diagnostics::Debug::WriteLineIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writelineif.aspx)|  
|[\_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|ヒープ内のすべての `_CLIENT_BLOCK` 型に対して、アプリケーションによって提供される関数を呼び出します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|重大なメモリ リークが発生したときに、デバッグ ヒープ内のすべてのメモリ ブロックをダンプします|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|指定されたメモリ ブロックがローカル ヒープ内にあり、有効なデバッグ ヒープ ブロック型識別子が設定されていることを確認します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|指定したポインターがローカル ヒープ内にあることを検証します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|指定したメモリ範囲で読み取りおよび書き込みが可能であることを確認します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|デバッグ ヒープの現在の状態を取得し、アプリケーションが指定した `_CrtMemState` 構造体に格納します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtMemDifference](../Topic/_CrtMemDifference.md)|2 つのメモリ状態の大幅な違いを比較し、結果を返します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtMemDumpAllObjectsSince](../Topic/_CrtMemDumpAllObjectsSince.md)|指定されたチェックポイントの取得以降、またはプログラムの実行開始以降の、ヒープ上のオブジェクトに関する情報をダンプします|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtMemDumpStatistics](../Topic/_CrtMemDumpStatistics.md)|指定されたメモリ状態のデバッグ ヘッダー情報をユーザーが判読できる形式でダンプします|[\<caps:sentence id\="tgt64" sentenceid\="e42975224af21ff11a761e6a6bdbd602" class\="tgtSentence"\>System::Diagnostics::PerformanceCounter\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.performancecounter.aspx)|  
|[\_CrtReportBlockType](../Topic/_CrtReportBlockType.md)|特定のデバッグ ヒープ ブロック ポインターに関連付けられたブロックの型および細分化された型を返します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtSetAllocHook](../Topic/_CrtSetAllocHook.md)|C ランタイム デバッグ メモリ割り当てプロセスにフックして、クライアント定義割り当て関数をインストールします|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|指定されたオブジェクト割り当て順序番号にブレークポイントを設定します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|`_crtDbgFlag` フラグの状態を取得または変更して、デバッグ ヒープ マネージャーの割り当て動作を制御します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|`_CLIENT_BLOCK` 型のメモリ ブロックをダンプするためにデバッグ ダンプ関数が呼び出されるたびに呼び出されるアプリケーション定義関数をインストールします|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtSetReportFile](../Topic/_CrtSetReportFile.md)|`_CrtDbgReport` による特定の種類のレポートの出力先として使用されるファイルまたはストリームを特定します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|C ランタイム デバッグ レポート プロセスにフックして、クライアント定義レポート関数をインストールします|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtSetReportHook2、\_CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|C ランタイム デバッグ レポート プロセスにフックして、クライアント定義レポート関数をインストールまたはアンインストールします。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|`_CrtDbgReport` によって生成される特定の種類のレポートの一般的な出力先を指定します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_RPT&#91;0,1,2,3,4&#93;](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md)|書式指定文字列と可変数の引数と共に `_CrtDbgReport` を呼び出してデバッグ レポートを生成することによって、アプリケーションの進行状況を追跡します。  ソース ファイルと行番号の情報は提供されません。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_RPTF&#91;0,1,2,3,4&#93;](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md)|`_RPTn` マクロに似ていますが、レポート要求の発生元となったソース ファイル名と行番号を提供します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_calloc\_dbg](../c-runtime-library/reference/calloc-dbg.md)|デバッグ ヘッダーと上書きバッファー用の追加の領域を持つ、指定された数のメモリ ブロックをヒープに割り当てます|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_expand\_dbg](../Topic/_expand_dbg.md)|ブロックの拡張や縮小によって、ヒープ内の指定されたメモリのブロックをサイズ変更します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_free\_dbg](../c-runtime-library/reference/free-dbg.md)|ヒープ上のメモリのブロックを解放します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_fullpath\_dbg、\_wfullpath\_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|指定された相対パス名の絶対または完全パス名を作成します。メモリを割り当てるために、[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md) が使用されます。|[\<caps:sentence id\="tgt129" sentenceid\="57f5d14fd2f1847b8e44146f72e48f72" class\="tgtSentence"\>System::IO::File::Create\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_getcwd\_dbg、\_wgetcwd\_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|現在の作業ディレクトリを取得します。メモリを割り当てるために、[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md) が使用されます。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md)|デバッグ ヘッダーと上書きバッファー用の追加の領域を持つ、メモリ ブロックをヒープに割り当てます|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_msize\_dbg](../c-runtime-library/reference/msize-dbg.md)|ヒープ内のメモリ ブロックのサイズを計算します|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_realloc\_dbg](../c-runtime-library/reference/realloc-dbg.md)|ブロックの移動やサイズ変更によって、ヒープ内の指定されたメモリのブロックを再割り当てします|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_strdup\_dbg、\_wcsdup\_dbg](../Topic/_strdup_dbg,%20_wcsdup_dbg.md)|文字列を複製します。メモリを割り当てるために、[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md) が使用されます。|[\<caps:sentence id\="tgt151" sentenceid\="74a4ca1462af4bfed5950888b5c554e1" class\="tgtSentence"\>System::String::Clone\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.string.clone.aspx)|  
|[\_tempnam\_dbg、\_wtempnam\_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|一時ファイルを作成するために使用できる名前を生成します。メモリを割り当てるために、[\_malloc\_dbg](../c-runtime-library/reference/malloc-dbg.md) が使用されます。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
  
 デバッグ ルーチンを使用して、デバッグ プロセス中にほとんどの他の C ランタイム ルーチンのソース コードをステップ実行することができます。  ただし、一部のテクノロジは Microsoft によって所有物と見なされるため、これらのルーチンにソース コードが提供されません。  これらのルーチンのほとんどは例外処理または浮動小数点処理のグループに属していますが、他のグループに属しているものもあります。  次の表は、これらのルーチンの一覧です。  
  
### ソース コードの形式で使用できない C ランタイム ルーチン  
  
||||  
|-|-|-|  
|[acos、acosf、acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|[\_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|[\_nextafter](../c-runtime-library/reference/nextafter-functions.md)|  
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[\_fpieee\_flt](../c-runtime-library/reference/fpieee-flt.md)|[pow](../Topic/pow,%20powf,%20powl.md)|  
|[atan、atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[\_fpreset](../c-runtime-library/reference/fpreset.md)|[printf、\_printf\_l、wprintf、\_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [printf\_s、\_printf\_s\_l、wprintf\_s、\_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)\*|  
|[\_cabs](../Topic/_cabs.md)|[frexp](../c-runtime-library/reference/frexp.md)|[\_scalb](../c-runtime-library/reference/scalb.md)|  
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|[\_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[scanf、\_scanf\_l、wscanf、\_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), [scanf\_s、\_scanf\_s\_l、wscanf\_s、\_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)\*|  
|[\_chgsign、\_chgsignf、\_chgsignl](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[\_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|  
|[\_clear87、\_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[\_j0](../misc/bessel-functions-j0-j1-jn.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)|[\_j1](../misc/bessel-functions-j0-j1-jn.md)|[sinh](../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)|  
|[copysign、copysignf、copysignl、\_copysign、\_copysignf、\_copysignl](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[\_jn](../misc/bessel-functions-j0-j1-jn.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|  
|[cos](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|[\_status87、\_statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|  
|[cosh](../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)|[log](../Topic/log,%20logf,%20log10,%20log10f.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[Exp](../c-runtime-library/reference/exp-expf.md)|[log10](../Topic/log,%20logf,%20log10,%20log10f.md)|[tanh](../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)|  
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[\_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[\_y0](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[\_finite](../c-runtime-library/reference/finite-finitef.md)|[longjmp](../c-runtime-library/reference/longjmp.md)|[\_y1](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|[\_matherr](../c-runtime-library/reference/matherr.md)|[\_yn](../Topic/Bessel%20Functions:%20_y0,%20_y1,%20_yn.md)|  
|[fmod](../Topic/fmod,%20fmodf.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)||  
  
 \*   このルーチンの大部分でソース コードを使用できますが、ソース コードが提供されない他のルーチンへの内部呼び出しが行われています。  
  
 一部の C ランタイム関数と C\+\+ 演算子は、アプリケーションのデバッグ ビルドから呼び出されたときの動作が異なります。アプリケーションのデバッグ ビルドは、`_DEBUG` フラグを定義するか、C ランタイム ライブラリのデバッグ バージョンとリンクすることによって作成できます。動作上の違いは、通常、デバッグ プロセスをサポートするために、機能が追加されたりルーチンによって情報が提供されたりすることです。  次の表は、これらのルーチンの一覧です。  
  
### アプリケーションのデバッグ ビルドでは動作が異なるルーチン  
  
|||  
|-|-|  
|C [abort](../c-runtime-library/reference/abort.md) ルーチン|C\+\+ [delete](../cpp/delete-operator-cpp.md) 演算子|  
|C [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) ルーチン|C\+\+ [new](../cpp/new-operator-cpp.md) 演算子|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [ランタイム エラー チェック](../Topic/Run-Time%20Error%20Checking.md)