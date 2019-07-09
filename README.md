## Reference:
Angular Style Guide: [https://angular.io/guide/styleguide](https://angular.io/guide/styleguide)
C# Style Guide: [https://github.com/MakingSense/code-style-guides/blob/master/CSharp/README.md](https://github.com/MakingSense/code-style-guides/blob/master/CSharp/README.md)

## Additional Style Guide:

**Controller naming convention**
Don't use "Async" in controller name. Since http controller is async by nature and will increase function name in ApiClient that resides in front end code.
   

     // Bad
     [HttpGet("[action]/{id}")]
     public Task<int> GetAccessLevelToDealAsync(int id)     
     
     // Good
     [HttpGet("[action]/{id}")]
     public Task<int> GetAccessLevelToDeal(int id)
     
**Callback variable naming**

    // Bad: rolePermission callback variable doesn't provide additional clarity
    const nzCheckedKeys = rolePermissions.map(rolePermission => rolePermission.permissionID);

	// Good: Short variable name for better readability
    const nzCheckedKeys = rolePermissions.map(m => m.permissionID);
    
    // Bad: Don't use short variable name if callback is more than 1 line. 
    // Reader can easily lose variable context
    const nzCheckedKeys = rolePermissions.map(m=> {
	    return {
		   permissionID: m.permissionID
		    };
	    });
    
    // Good: Descriptive variable name for better readability if callback is more than 1 line. 
    const nzCheckedKeys = rolePermissions.map(rolePermission=> {
	    return {
		   permissionID: rolePermission.permissionID
		    };
	    });


**Boolean comparison**  
Avoid compare boolean type with boolean
 

     // Bad
     if(isAdmin == true){}
     
     // Good
     if(isAdmin){}
     
     // Bad
     if(isAdmin == false){}
     
     // Good
     if(!isAdmin){}
     
Avoid null or undefined check when comparing boolean
 

     // Bad
     if(isAdmin != null && isAdmin !== undefined && isAdmin){}
     
     // Good
     if(isAdmin){}
     
     // Bad
     if(isAdmin == null || isAdmin === undefined || !isAdmin){}
     
     // Good
     if(!isAdmin){}
     

