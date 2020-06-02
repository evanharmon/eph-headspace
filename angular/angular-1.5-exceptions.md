# ANGULAR 1.5 EXCEPTIONS

## Force Angular to Throw Exceptions instead of Console Logging Them
(http://stackoverflow.com/questions/13595469/how-to-override-exceptionhandler-implementation)

## Force Browser to throw exception without setting breakpoint
Angular 1.4.8 line 16157, comment out exception handler in purple font below
 ```
 * Scope's `$apply()` method transitions through the following stages:
 *
 * 1. The {@link guide/expression expression} is executed using the
 *    {@link ng.$rootScope.Scope#$eval $eval()} method.
 * 2. Any exceptions from the execution of the expression are forwarded to the
 *    {@link ng.$exceptionHandler $exceptionHandler} service.
 * 3. The {@link ng.$rootScope.Scope#$watch watch} listeners are fired immediately after the
 *    expression was executed using the {@link ng.$rootScope.Scope#$digest $digest()} method.
 *
 *
 * @param {(string|function())=} exp An angular expression to be executed.
 *
 *    - `string`: execute using the rules as defined in {@link guide/expression expression}.
 *    - `function(scope)`: execute the function with current `scope` parameter.
 *
 * @returns {*} The result of evaluating the expression.
 */
 $apply: function(expr) {
   try {
     beginPhase('$apply');
     try {
       return this.$eval(expr);
     } finally {
       clearPhase();
     }
   } catch (e) {
     $exceptionHandler(e);
   } finally {
     try {
       $rootScope.$digest();
     } catch (e) {
       $exceptionHandler(e);
       throw e;
     }
   }
 },
 ```
