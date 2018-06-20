---
layout: post
title: Use tensorflow to calculate symbolic derivatives of a function (minimal example)
category: memo programming
comments: true


---

I was using Theano to calculate the jacobian and hessian of some functions in my Python code, but Theano has been "discontinued".

So how can I replace Theano with some other supported library?

Tensorflow is a possible alternative, but the library and its jargoon is mainly oriented to DeepLearning tasks. So, doing something as simple as getting the symbolic derivative of a function gets "linguistically" complicated... but we'll see that it's not difficult to achieve in TensorFlow... actually it's quite the opposite!

I want to give you a minimal example, then you can build on it.

```python
import tensorflow as tf

# get a number from terminal
print("type a number and press enter")
point = input()
point = int(point)
data = tf.placeholder(dtype=tf.float32, shape=())

# the function you want to calculate the gradient
def funct(indata):
    square = tf.pow(indata, 2)
        return square

# start a TensorFlow session (you need it to evaluate numerically the symbolic expressions)
sess = tf.Session()

tf_funct = funct(data)  # TF symbolic version of funct
val_funct = tf_funct.eval(feed_dict={data: point}, session=sess)  # value of funct in your point
print("The value you entered squared: %.1f" % val_funct)

grad_funct = tf.gradients(tf_funct, [data])[0]  # calculate the gradient of funct
val_grad_funct = grad_funct.eval(feed_dict={data: point}, session=sess)  # evaluate the gradient in your point
print("Twice the value you entered: %.1f" % val_grad_funct)

```

Easy!
HTH

