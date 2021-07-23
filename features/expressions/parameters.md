## Static parameters

Static parameters are values which can be defined before the evaluation of an expression.
These parameters can be accesed using the **Parameters** dictionary of the **Expression** instance.

{code:c#}
  Expression e = new Expression("2 * [x](x) ^ 2 + 5 * [y](y)");
  e.Parameters["x"](_x_) = 5;
  e.Parameters["y"](_y_) = 1;

  Console.WriteLine(e.Evaluate());
{code:c#}

Parameters can be useful when a value is unknown at compile time, or when performance is important and the parsing can be saved for further calculations.

## Expression parameters

Expressions can be splitted into several ones by defining expression parameters. Those parameters are not simple values but **Expression** instances themselves.

{code:c#}
  Expression volume = new Expression("[surface](surface) * h");
  Expression surface = new Expression("[l](l) * [L](L)");
  volume.Parameters["surface"](_surface_) = surface;
  surface.Parameters["l"](_l_) = 1;
  surface.Parameters["L"](_L_) = 2;
{code:c#}

## Dynamic parameters

Sometimes parameters can be even more complex to evaluate and need a dedicated method to be evaluated. This can be done by intercepting there evaluation using the **EvaluateParameter** event published on **Expression** instances. Thus, each time a parameter is not defined in the dictionary, this event is called to try to resolve the value.

{code:c#}
  Expression e = new Expression("Round(Pow([Pi](Pi)(Pi), 2) + Pow([Pi](Pi)(Pi), 2) + [X](X), 2)");

  e.Parameters["Pi2"](_Pi2_) = new Expression("Pi * [Pi](Pi)");
  e.Parameters["X"](_X_) = 10;

  e.EvaluateParameter += delegate(string name, ParameterArgs args)
    {
      if (name == "Pi")
        args.Result = 3.14;
    };
{code:c#}

## Square brackets parameters

Parameters in between square brackets can contain special characters like spaces, dots, and also start with digits.

{code:c#}
  Expression e = new Expression("[My First Parameter](My-First-Parameter) + [My Second Parameter](My-Second-Parameter)");
{code:c#}

## Multi-valued parameters

When parameters are IEnumerable and the **EvaluationOptions.IterateParameters** is used, the result is an **IList** made of the evaluation of each value in the parameter.

{code:c#}
 Expression e = new Expression("(a * b) ^ c", EvaluateOption.IterateParameters);
 e.Parameters["a"](_a_) = new int[]() { 1, 2, 3, 4, 5 };
 e.Parameters["b"](_b_) = new int[]() { 6, 7, 8, 9, 0 };
 e.Parameters["c"](_c_) = 3;

 foreach (var result in (IList)e.Evaluate())
 {
     Console.WriteLine(result);
 }

 //  216
 //  2744
 //  13824
 //  46656
 //  0
{code:c#}
