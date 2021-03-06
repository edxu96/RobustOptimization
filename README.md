# RobustOptim
Introductory (adjustable) robust optimization by matrix computation.

Detailed explanation can be found in file [Cookbook for Robust Optimization, EDXU](files/cookbook.pdf)

This repo has been archived in 190728. New update will be made to [edxu96/MatrixOptim](https://github.com/edxu96/MatrixOptim), which is the aggregation of robust optimization and matrix optimization. It's in matrix form as well, and there is a new function tool to convert the model to matrix form.

## How to make robust optimization less conservative?

- Use of different uncertainty sets by including restricting the uncertainty sets, e.g. using 95% confidence interval  
- Use a budget of uncertainty, so not all parameters can take their worst case  
- Introduce recourse decisions to form adjustable robust optimization  

## RO with Box Uncertainty and Budget of Uncertainty

```Julia
RobustMilpBoxBudget(; num_x, num_y, vec_min_y, vec_max_y, vec_c, vec_f, vec_b, mat_a, mat_b,
    mat_a_bar, mat_a_hat, mat_b_bar, vec_b_bar, vec_gammaCap)
```

## RO of Two-Stage Stochastic LP with Box Uncertainty

```Julia
milpAdjustBox(; num_x, num_y, num_z, vec_min_y, vec_max_y, vec_c, vec_f, vec_g, vec_b,
    mat_a, mat_b, mat_d, mat_a_bar, mat_a_hat, mat_b_bar, mat_d_bar, vec_b_bar)
```

## Examples

### Example 1: Production Planning with Uncertainty in Production Efficiency

Formulate a robust optimization model that decides the number of machines and production quantities for each product and machine to have minimal cost and cover the demand in all cases of production time deviation. Use a budget of uncertainty.

Problem description can be found in first example of file [Cookbook for Robust Optimization, EDXU](files/cookbook.pdf). There are form of solutions in Julia, with one in matrix form and one in traditional form.

### Example 2: Production Planning of Two-Stage Stochastic LP with Box Uncertainty

Problem description can be found in second example of file [Cookbook for Robust Optimization, EDXU](files/cookbook.pdf). There are form of solutions in Julia, with one in matrix form and one in traditional form.

***

Author: Edward J. Xu, edxu96@outlook.com  
Last Update Date: April 8th, 2019
