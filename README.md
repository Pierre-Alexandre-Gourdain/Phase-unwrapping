# The phase unwrapping of under-sampled interferograms using compact radial basis function neural networks
We are using non-linear regression coupled to a physics informed neutral network to unwrap the phase measured by interferometry. The newrok relies on:
1. radial basis functions, which insures that the unwrapped phase is smooth;
2. the wrapping operator, which removes phase jumps from the wrapped phase derivatives
3. the sine and cosine operators, which are oblivious of phase jumps.

The combinations of physics operators with a Levenberg-Marquardt algorithm minimize the error between the wrapped measured phase as if the phase was unwrapped. As a result, the algorithm achieves super-resolution, where phase unwrapping becomes possible even if when the phase was wrapped multiple times across one pixel, provinding that noises levels are reasonable.

There is a serial version and a parallel version. Since numpy does a system solve in parallel, there is no point in running the code in parallel so each parallel section is running one after the other, so it effectively runs in parallel. However, matrices are much reduced is size due to domain decomposition.

If you find this software useful and used it inside a publication, use the reference below in your bibliography:<br>
https://arxiv.org/abs/2210.10541

This work was supported by the NSF under the grant number PHY-1943939.
