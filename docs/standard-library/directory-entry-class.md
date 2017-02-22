---
title: "directory_entry クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator const std::experimental::filesystem::v1::path &"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "std::experimental::filesystem::v1::directory_entry::directory_entry"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator="
  - "std::experimental::filesystem::v1::directory_entry::operator="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::assign"
  - "std::experimental::filesystem::v1::directory_entry::assign"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "std::experimental::filesystem::v1::directory_entry::replace_filename"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::path"
  - "std::experimental::filesystem::v1::directory_entry::path"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::status"
  - "std::experimental::filesystem::v1::directory_entry::status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "std::experimental::filesystem::v1::directory_entry::symlink_status"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<"
  - "std::experimental::filesystem::v1::directory_entry::operator<"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator=="
  - "std::experimental::filesystem::v1::directory_entry::operator=="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator!="
  - "std::experimental::filesystem::v1::directory_entry::operator!="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator<="
  - "std::experimental::filesystem::v1::directory_entry::operator<="
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>"
  - "std::experimental::filesystem::v1::directory_entry::operator>"
  - "FILESYSTEM/std::experimental::filesystem::v1::directory_entry::operator>="
  - "std::experimental::filesystem::v1::directory_entry::operator>="
dev_langs: 
  - "C++"
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# directory_entry クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`*X` によって返されるオブジェクトを表します。ここで *X* は、[directory\_iterator](../Topic/directory_iterator%20Class.md) または [recursive\_directory\_iterator](../Topic/recursive_directory_iterator%20Class.md) です。  
  
## 構文  
  
```  
class directory_entry;  
```  
  
## 解説  
 このクラスは [path クラス](../Topic/path%20Class%20\(C++%20Standard%20Template%20Library\).md)型のオブジェクトを格納します。`path` は、[path](../Topic/path%20Class%20\(C++%20Standard%20Template%20Library\).md)、または `path` から派生した型になります。 また、2 つの [file\_type](../Topic/file_type%20Enumeration.md) 値も格納します。1 つは格納されたファイル名の状態に関する既知の情報を表し、もう 1 つはファイル名のシンボリック リンクの状態に関する既知の情報を表します。  
  
 詳細およびコード例については、「[ファイル システムのナビゲーション \(C\+\+\)](../standard-library/file-system-navigation.md)」を参照してください。  
  
## assign  
  
```  
void assign(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 このメンバー関数は、pval を mypath に、stat を mystat に、symstat を mysymstat に割り当てます。  
  
## directory\_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 既定のコンストラクターは想定どおりの動作をします。 4 番目のコンストラクターは、mypath を pval に、mystat を stat\_arg に、mysymstat を symstat\_arg に初期化します。  
  
## operator\!\=  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
  
```  
  
 このメンバー関数は \!\(\*this \=\= right\) を返します。  
  
## operator\=  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
  
```  
  
 この既定のメンバー代入演算子は想定どおりに動作します。  
  
## operator\=\=  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数は mypath \=\= right.mypath を返します。  
  
## operator\<  
  
```  
  
bool operator<(const directory_entry& right) const noexcept;  
  
```  
  
 このメンバー関数は mypath \< right.mypath を返します。  
  
## operator\<\=  
  
```  
bool operator<=(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数は \!\(right \< \*this\) を返します。  
  
## operator\>  
  
```  
bool operator>(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数は right \< \*this を返します。  
  
## operator\>\=  
  
```  
bool operator>=(const directory_entry& right) const noexcept;  
  
```  
  
 このメンバー関数は \!\(\*this \< right\) を返します。  
  
## operator const path\_type&  
  
```  
operator const path&() const; // retained  
```  
  
 このメンバー演算子は mypath を返します。  
  
## path  
  
```  
const PFX path& path() const noexcept;  
```  
  
 このメンバー関数は mypath を返します。  
  
## replace\_filename  
  
```  
void replace_filename(const PFX path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());  
```  
  
 このメンバー関数は、mypath を mypath.parent\_path\(\) \/ pval、mystat を stat\_arg、mysymstat を symstat\_arg と置き換えます。  
  
## 状態  
  
```  
file_status status() const;  
file_status status(  
    error_code& ec) const noexcept;  
Otherwise, mystat = status(mypval).  
  
```  
  
 メンバー関数はどちらも、恐らく最初に mystat を次のように変更し、それからこれを返します。  
  
1.  status\_known\(mystat\) の場合は何も実行しません。  
  
2.  それ以外の場合は、\!status\_known\(mysymstat\) && \!is\_symlink\(mysymstat\) であれば mystat \= mysymstat です。  
  
## symlink\_status  
  
```  
file_status symlink_status() const;  
file_status symlink_status(  
    error_code& ec) const noexcept;  
```  
  
 メンバー関数ではどちらも、恐らく最初に mysymstat を次のように変更し、それからこれを返します。status\_known\(mysymstat\) の場合は何もしません。 それ以外の場合、mysymstat \= symlink\_status\(mypval\) です。  
  
## 必要条件  
 **ヘッダー:** filesystem  
  
 **名前空間:** std::tr2::sys  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../Topic/%3Cfilesystem%3E.md)