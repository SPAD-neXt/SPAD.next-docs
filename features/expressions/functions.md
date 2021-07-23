# Functions

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Usage</th>
      <th style="text-align:left">Result</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Abs</b>
      </td>
      <td style="text-align:left">Returns the absolute value of a specified number.</td>
      <td style="text-align:left">Abs(-1)</td>
      <td style="text-align:left">1M</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Acos</b>
      </td>
      <td style="text-align:left">Returns the angle whose cosine is the specified number.</td>
      <td style="text-align:left">Acos(1)</td>
      <td style="text-align:left">0d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Asin</b>
      </td>
      <td style="text-align:left">Returns the angle whose sine is the specified number.</td>
      <td style="text-align:left">Asin(0)</td>
      <td style="text-align:left">0d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Atan</b>
      </td>
      <td style="text-align:left">Returns the angle whose tangent is the specified number.</td>
      <td style="text-align:left">Atan(0)</td>
      <td style="text-align:left">0d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Ceiling</b>
      </td>
      <td style="text-align:left">Returns the smallest integer greater than or equal to the specified number.</td>
      <td
      style="text-align:left">Ceiling(1.5)</td>
        <td style="text-align:left">2d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Cos</b>
      </td>
      <td style="text-align:left">Returns the cosine of the specified angle.</td>
      <td style="text-align:left">Cos(0)</td>
      <td style="text-align:left">1d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Exp</b>
      </td>
      <td style="text-align:left">Returns e raised to the specified power.</td>
      <td style="text-align:left">Exp(0)</td>
      <td style="text-align:left">1d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Floor</b>
      </td>
      <td style="text-align:left">Returns the largest integer less than or equal to the specified number.</td>
      <td
      style="text-align:left">Floor(1.5)</td>
        <td style="text-align:left">1d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>IEEERemainder</b>
      </td>
      <td style="text-align:left">Returns the remainder resulting from the division of a specified number
        by another specified number.</td>
      <td style="text-align:left">IEEERemainder(3, 2)</td>
      <td style="text-align:left">-1d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Log</b>
      </td>
      <td style="text-align:left">Returns the logarithm of a specified number.</td>
      <td style="text-align:left">Log(1, 10)</td>
      <td style="text-align:left">0d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Log10</b>
      </td>
      <td style="text-align:left">Returns the base 10 logarithm of a specified number.</td>
      <td style="text-align:left">Log10(1)</td>
      <td style="text-align:left">0d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Max</b>
      </td>
      <td style="text-align:left">Returns the larger of two specified numbers.</td>
      <td style="text-align:left">Max(1, 2)</td>
      <td style="text-align:left">2</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Min</b>
      </td>
      <td style="text-align:left">Returns the smaller of two numbers.</td>
      <td style="text-align:left">Min(1, 2)</td>
      <td style="text-align:left">1</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Pow</b>
      </td>
      <td style="text-align:left">Returns a specified number raised to the specified power.</td>
      <td style="text-align:left">Pow(3, 2)</td>
      <td style="text-align:left">9d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Round</b>
      </td>
      <td style="text-align:left">Rounds a value to the nearest integer or specified number of decimal places.
        The mid number behaviour can be changed by using EvaluateOption.RoundAwayFromZero
        during construction of the Expression object.</td>
      <td style="text-align:left">Round(3.222, 2)</td>
      <td style="text-align:left">3.22d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Sign</b>
      </td>
      <td style="text-align:left">Returns a value indicating the sign of a number.</td>
      <td style="text-align:left">Sign(-10)</td>
      <td style="text-align:left">-1</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Sin</b>
      </td>
      <td style="text-align:left">Returns the sine of the specified angle.</td>
      <td style="text-align:left">Sin(0)</td>
      <td style="text-align:left">0d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Sqrt</b>
      </td>
      <td style="text-align:left">Returns the square root of a specified number.</td>
      <td style="text-align:left">Sqrt(4)</td>
      <td style="text-align:left">2d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Tan</b>
      </td>
      <td style="text-align:left">Returns the tangent of the specified angle.</td>
      <td style="text-align:left">Tan(0)</td>
      <td style="text-align:left">0d</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Truncate</b>
      </td>
      <td style="text-align:left">Calculates the integral part of a number.</td>
      <td style="text-align:left">Truncate(1.7)</td>
      <td style="text-align:left">1</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Timespan</b>
      </td>
      <td style="text-align:left">Takes a number and interprets it a a timespan in milliseconds</td>
      <td
      style="text-align:left">Timespan(1000)</td>
        <td style="text-align:left">00:00:01.00</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>ToNumber</b>
      </td>
      <td style="text-align:left">Converts the argument into a number (e.g. if it&apos;s a string)</td>
      <td
      style="text-align:left">
        <p>ToNumber(&apos;100&apos;)</p>
        <p>ToNumber([SIMCONNECT:ATC])</p>
        </td>
        <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>ToString</b>
      </td>
      <td style="text-align:left">Converts the argument into a string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>GetValue</b>
      </td>
      <td style="text-align:left">Get the Value of the Reference the argument is pointing to.</td>
      <td style="text-align:left">GetValue(&apos;SIMCONNECT:ATC&apos;)</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Format</b>
      </td>
      <td style="text-align:left">Formats argument-1 using the formating rule argument-2</td>
      <td style="text-align:left">Format( 123.2356 , &apos;0.00&apos; )</td>
      <td style="text-align:left">123.23</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>SubStr</b>
      </td>
      <td style="text-align:left">Extracts a subsctring SubStr(value, startIndex, [length])</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Len</b>
      </td>
      <td style="text-align:left">Gets the Length of the argument as string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>ToBCO16</b>
      </td>
      <td style="text-align:left">Convert argument to BCO16</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>FromBCO16</b>
      </td>
      <td style="text-align:left">Convert argument from a number to BCO16</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>



