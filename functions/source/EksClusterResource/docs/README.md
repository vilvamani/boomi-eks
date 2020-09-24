# AWSQS::EKS::Cluster

A resource that creates EKS clusters.

## Syntax

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON

<pre>
{
    "Type" : "AWSQS::EKS::Cluster",
    "Properties" : {
        "<a href="#name" title="Name">Name</a>" : <i>String</i>,
        "<a href="#rolearn" title="RoleArn">RoleArn</a>" : <i>String</i>,
        "<a href="#version" title="Version">Version</a>" : <i>String</i>,
        "<a href="#resourcesvpcconfig" title="ResourcesVpcConfig">ResourcesVpcConfig</a>" : <i><a href="resourcesvpcconfig.md">ResourcesVpcConfig</a></i>,
        "<a href="#enabledclusterloggingtypes" title="EnabledClusterLoggingTypes">EnabledClusterLoggingTypes</a>" : <i>[ String, ... ]</i>,
        "<a href="#encryptionconfig" title="EncryptionConfig">EncryptionConfig</a>" : <i>[ <a href="encryptionconfig.md">EncryptionConfig</a>, ... ]</i>,
        "<a href="#kubernetesapiaccess" title="KubernetesApiAccess">KubernetesApiAccess</a>" : <i><a href="kubernetesapiaccess.md">KubernetesApiAccess</a></i>,
    }
}
</pre>

### YAML

<pre>
Type: AWSQS::EKS::Cluster
Properties:
    <a href="#name" title="Name">Name</a>: <i>String</i>
    <a href="#rolearn" title="RoleArn">RoleArn</a>: <i>String</i>
    <a href="#version" title="Version">Version</a>: <i>String</i>
    <a href="#resourcesvpcconfig" title="ResourcesVpcConfig">ResourcesVpcConfig</a>: <i><a href="resourcesvpcconfig.md">ResourcesVpcConfig</a></i>
    <a href="#enabledclusterloggingtypes" title="EnabledClusterLoggingTypes">EnabledClusterLoggingTypes</a>: <i>
      - String</i>
    <a href="#encryptionconfig" title="EncryptionConfig">EncryptionConfig</a>: <i>
      - <a href="encryptionconfig.md">EncryptionConfig</a></i>
    <a href="#kubernetesapiaccess" title="KubernetesApiAccess">KubernetesApiAccess</a>: <i><a href="kubernetesapiaccess.md">KubernetesApiAccess</a></i>
</pre>

## Properties

#### Name

The unique name to give to your cluster.

_Required_: No

_Type_: String

_Update requires_: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

#### RoleArn

The Amazon Resource Name (ARN) of the IAM role that provides permissions for Amazon EKS to make calls to other AWS API operations on your behalf.

_Required_: Yes

_Type_: String

_Update requires_: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

#### Version

The desired Kubernetes version for your cluster. If you don't specify a value here, the latest version available in Amazon EKS is used.

_Required_: No

_Type_: String

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

#### ResourcesVpcConfig

An object representing the VPC configuration to use for an Amazon EKS cluster.



_Required_: Yes

_Type_: <a href="resourcesvpcconfig.md">ResourcesVpcConfig</a>

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

#### EnabledClusterLoggingTypes

Enable exporting the Kubernetes control plane logs for your cluster to CloudWatch Logs. By default, cluster control plane logs aren't exported to CloudWatch Logs. Valid log types are api, audit, authenticator, controllerManager and scheduler

_Required_: No

_Type_: List of String

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

#### EncryptionConfig

The encryption configuration for the cluster.

_Required_: No

_Type_: List of <a href="encryptionconfig.md">EncryptionConfig</a>

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

#### KubernetesApiAccess

_Required_: No

_Type_: <a href="kubernetesapiaccess.md">KubernetesApiAccess</a>

_Update requires_: [No interruption](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-no-interrupt)

## Return Values

### Ref

When you pass the logical ID of this resource to the intrinsic `Ref` function, Ref returns the Name.

### Fn::GetAtt

The `Fn::GetAtt` intrinsic function returns a value for a specified attribute of this type. The following are the available attributes and sample return values.

For more information about using the `Fn::GetAtt` intrinsic function, see [Fn::GetAtt](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-getatt.html).

#### Arn

The ARN of the cluster, such as arn:aws:eks:us-west-2:666666666666:cluster/prod.

#### Endpoint

The endpoint for your Kubernetes API server, such as https://5E1D0CEXAMPLEA591B746AFC5AB30262.yl4.us-west-2.eks.amazonaws.com.

#### ClusterSecurityGroupId

The cluster security group that was created by Amazon EKS for the cluster. Managed node groups use this security group for control plane to data plane communication.

#### CertificateAuthorityData

The certificate-authority-data for your cluster.

#### EncryptionConfigKeyArn

Amazon Resource Name (ARN) or alias of the customer master key (CMK).

#### OIDCIssuerURL

The issuer URL for the OpenID Connect identity provider.

