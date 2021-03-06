# Xamarin Kick Starter Template

Get Up and running with your _Xamarin Forms_ project in no time, use this template to get an new xamarin forms project with a MVVM Folder structure, The most used nuget packeges and services with the latest .netStanderd 2.1 and C# 8 with the push of a single button.

## How to use it?

Just Click _Use This Template_ in the Project's Github Repo.

![Xamarin Kick Start Template](https://i.ibb.co/WFczbWN/template.png)

## Why Should You Use it?
The _Xamarin Kick Starter Template_ Cuts the project start overhead by providing you with some of the most commonly used services and nugets packs for every Xamarin Forms Project.

## Basic Features
_This Template is based upon our Own Modified Version Of [Fresh MVVM](https://github.com/rid00z/FreshMvvm)_ , [Xamarin forms](https://github.com/xamarin/Xamarin.Forms) and [Xamarin Essentials](https://github.com/xamarin/Essentials).

* MVVM File Structure (with some extra folders for Converters, Custom Controls, etc...).

* PageModel to PageModel Navigation

* Automatic wiring of BindingContext

* Automatic wiring of Page events (eg. appearing)

* Basic methods (with values) on PageModel (init, reverseinit)

* Built in IOC Container

## Additional Features

* Automatic Refresh on Property Change using  [PropertyChanged.Fody](https://github.com/Fody/PropertyChanged).

* Elements State managment using [Xamarin.Forms.StateSquid](https://github.com/sthewissen/Xamarin.Forms.StateSquid).

* User Dialogs and loading Screens using [ACR User Dialogs](https://github.com/aritchie/userdialogs).

* Json Serialization and Deserialization Using [Newtonsoft.Json](https://www.newtonsoft.com/json).

* Media Plugin for Xamarin Using [MediaPlugin](https://github.com/jamesmontemagno/MediaPlugin).

* Weak Event Handeling

* Async Command Support

## HomeGrown Features

* In Memory LCS (Longest Common Subsequence) Generic Search.

* SQL Lite Local Database Service.

* String formating extensions.

* NullorEmpty checks inside the Objects\*.(for string feilds only).


## More Details on HomeGrown Features

### In Memory LCS (Longest Common Subsequence) Generic Search

All it needs is the collection you what to search in , the name of the property or the expression you are searching for and your search query

\* All string comparisons are done using the LCS (Longest Common Subsequence) Algorithm more on that [Here](https://www.geeksforgeeks.org/longest-common-subsequence-dp-4/).

``` c#
        /// <summary>
        ///     Returns objects in the collection where its target property is identical or similar to the query string
        /// </summary>
        /// <typeparam name="T"></typeparam>
        /// <param name="collection"></param>
        /// <param name="targetProperty"></param>
        /// <param name="query"></param>
        /// <returns></returns>
        public static IEnumerable<T> SearchInCollection<T>(IEnumerable<T> collection, string targetProperty, string query)
```

or 

``` c#
       /// <summary>
        ///     Returns objects in the collection where its target property is identical or similar to the query string
        /// </summary>
        /// <typeparam name="T"></typeparam>
        /// <param name="collection"></param>
        /// <param name="targetPropertyFunc"></param>
        /// <param name="query"></param>
        /// <returns></returns>
        public static IEnumerable<T> SearchInCollection<T>(IEnumerable<T> collection, Func<T, string> targetPropertyFunc,string query)
```


### SQL Lite Local Database Service

Get all what you need from a local database just at your finger tips with the ```ILocalDatabaseService``` interface

``` C#
 public interface ILocalDatabaseService
    {
        Task CreateDatabaseTables(List<Type> tables);
        Task CreateDatabaseTables(List<Type> tables,CreateFlags tableCreateFlags);
        Task<List<T>> GetAll<T>() where T : class, new();
        Task<int> Insert(object item);
        Task<int> InsertAll<T>(List<T> items) where T : new();
        Task<int> Update(object item);
        Task<int> UpdateAll<T>(List<T> items) where T : new();
        Task<int> Delete(object obj);
        Task<int> DeleteAll<T>() where T : new();
        Task<int> DropTableAsync<T>() where T : new();
        Task<IList<T>> QueryString<T>(string sql) where T : class, new();
        Task<List<SQLiteConnection.ColumnInfo>> GetTableInfo(string tableName);
        Task<List<T>> GetAll<T>(Expression<Func<T, bool>> query) where T : new();
        Task<T> GetOne<T>(Expression<Func<T, bool>> query) where T : class, new();
        Task InsertOrReplaceAll<T>(List<T> items) where T : new();
        Task<int> InsertOrReplaceOne<T>(object item) where T : new();
        Task DeleteAll<T>(List<T> items) where T : new();
        Task<int> ExecuteAsync(string sqlQuery);
    }
```

## Future Work

* Local Notifications Service

* Set MasterDetailsPage Design 

* Async Command Set task Result (to prevent multiple clicks on any giving button)

* On the Fly object validators 

* Basic Converters

## Issues and Bugs Reporting  

For any issue or bug found please open an _issue_ stating 
1. What was your expected output?

1. What was the actual output?

1. Any supprting screen shots or code snippits 


## Contributing 

Contributing is most welcomed you can contribute by 

1. sending a pull request that includes your changes and suggestions

or 

2. Opening up an issue explaining the suggestion or the feature with an enhancment tag on it





