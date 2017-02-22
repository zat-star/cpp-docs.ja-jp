---
title: "ctype &lt; char &gt; クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ctype<char>"
  - "locale/std::ctype<char>"
  - "std::ctype<char>"
  - "std.ctype<char>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype < char > クラス"
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# ctype &lt; char &gt; クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラスの明示的な特殊化は、クラスは **ctype \< CharType**> を入力する `char`, 、型の文字のさまざまなプロパティの内容を表すロケール ファセットとして使用できるオブジェクトを記述する `char`です。  
  
## <a name="syntax"></a>構文  
  
```  
template <>  
class ctype<char>  
: public ctype_base  
{  
public:  
    typedef char _Elem;  
    typedef _Elem char_type;  
    bool is(
    mask _Maskval,  
    _Elem _Ch) const;

 
    const _Elem* is(
    const _Elem* first,  
    const _Elem* last,  
    mask* dest) const;

 
    const _Elem* scan_is(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    const _Elem* scan_not(
    mask _Maskval,  
    const _Elem* first,  
    const _Elem* last) const;

 
    _Elem tolower(
    _Elem _Ch) const;

 
    const _Elem* tolower(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem toupper(
    _Elem _Ch) const;

 
    const _Elem* toupper(
    _Elem* first,  
    const _Elem* last) const;

 
    _Elem widen(
    char _Byte) const;

 
    const _Elem* widen(
    const char* first,  
    const char* last,  
    _Elem* dest) const;

 
    const _Elem* _Widen_s(
    const char* first,  
    const char* last,  
    _Elem* dest,  
    size_t dest_size) const;

 
    _Elem narrow(
    _Elem _Ch,  
    char _Dflt = '\0') const;

 
    const _Elem* narrow(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest) const;

 
    const _Elem* _Narrow_s(
    const _Elem* first,  
    const _Elem* last,  
    char _Dflt,  
    char* dest,  
    size_t dest_size) const;

 
    static locale::id& id;  
    explicit ctype(
    const mask* _Table = 0,  
    bool _Deletetable = false,  
    size_t _Refs = 0);

protected:  
    virtual ~ctype();
//other protected members  
};  
```  
  
## <a name="remarks"></a>解説  
 明示的な特殊化は、このテンプレート クラスは、いくつかの方法によって異なります。  
  
-   Ctype のクラスのオブジェクト < `char`> ctype マスク テーブルの最初の要素、UCHAR_MAX の配列 + 型の 1 要素へのポインターを格納 **ctype_base::mask**します。 配列を削除するかどうかを示すブール型のオブジェクトも格納 (を使用して `operator delete[]`) ときに、ctype \< **Elem**> オブジェクトを破棄します。  
  
-   唯一のパブリック コンス トラクターを指定できます。 **タブ**, 、ctype マスク テーブルと **del**, 、配列である場合は true ブール型のオブジェクト時に削除、ctype < `char`> 参照カウント パラメーター refs だけでなく、オブジェクトが破棄されます。  
  
-   保護されたメンバー関数は、 **テーブル** ストアド ctype マスク テーブルを返します。  
  
-   静的メンバー オブジェクト **table_size** ctype マスク テーブル内の要素の最小数を指定します。  
  
-   保護されている静的メンバー関数は、 **classic_table**(テーブルを返します ctype マスク"C"ロケールに対応します。  
  
-   プロテクト仮想メンバー関数が存在しない [do_is](../standard-library/ctype-class.md#ctype__do_is), 、[do_scan_is](../standard-library/ctype-class.md#ctype__do_scan_is), 、または [do_scan_not](../standard-library/ctype-class.md#ctype__do_scan_not)します。 対応するパブリック メンバー関数は、自分自身同等の操作を実行します。  
  
 メンバー関数は、 [do_narrow](../standard-library/ctype-class.md#ctype__do_narrow) と [do_widen](../standard-library/ctype-class.md#ctype__do_widen) 変更せずに要素をコピーします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \< ロケール>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [facet クラス](../Topic/facet%20Class.md)   
 [ctype_base クラス](../standard-library/ctype-base-class.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

